---
layout: post
title : Xcode中C++头文件的处理
header : Xcode中C++头文件的处理
group: navigation
---

####问题描述
在C++方面一直比较生疏，今天想使用集成flatbuffers到自己的项目中去，由于cocos2d-x 3.3版本已经自带了flatbuffers，所以直接使用了
cocos中flatbuffers得版本。但是集成时，include "flatbuffers/flatbuffers.h"会出现找不到的问题。
如果使用include "flatbuffers.h"就可以。

####问题解决
在查询了各种解决头文件的方案中，最终使用了Build Phases中使用Headers解决最佳。
具体操作：点击工程->Build Phases->点击右上+号 ->点击New Headers Phase->拖入工程中的头文件到Header选项中子项目 Project下即可。

