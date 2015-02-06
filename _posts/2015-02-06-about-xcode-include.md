---
layout: post
title : Xcode中C++头文件的处理
header : Xcode中C++头文件的处理
group: navigation
---

####问题描述
在C++方面一直比较生疏，今天想使用集成flatbuffers到自己的项目中去，由于cocos2d-x 3.3版本已经自带了flatbuffers，所以直接使用了cocos中flatbuffers得版本。<br>
但是集成时，include "flatbuffers/flatbuffers.h"会出现找不到的问题。如果使用include "flatbuffers.h"就可以。

####问题解决
通过研究cocos2d-x 3.0的XCode的工程组织方式，大概明白一些。<br>
当我们组织include文件的时候，可能根据库的类型组织，比如flatbuffers放到Project/external/flattbuffers/。<br>
这个时候如果直接添加external到工程中，默认创建了Group external之后，应用头文件就只能使用
"flatbuffers.h"的方式引用。<br>
如果想使用"flatbuffers/flatbuffers.h"，就需要添加 $(SRCROOT)/external 到User Header Search Paths中去。<br>
添加之后，我们#include的时候可以发现，两种方式的#include都可以使用。
#include "flatbuffers.h"
#include "flatbuffers/flatbuffers.h"
<br>
这里也可以看出，external的路径关联是可以去掉的。这样我们可以新建一个external组，但是不用和任何具体的路径关联，然后添加flatbuffers到external中去，然后添加User Header Search Paths即可。这样减少external目录修改产生的大量库文件需要重新添加的问题。




