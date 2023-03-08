---
layout: post
title: "Pagination Post"
author: "방지현"
tags: Javascript
---

Here we see **Tale's** pagination feature in action. It is set to 5 posts per page by default. Feel free to change this number in the `_config.yml` file!

# switch 문

### **switch, case**

조건에 따라 프로그램의 흐름을 분기해서 특정 코드가 실행되도록 함

`switch( */*비교할 값*/* ){
    case */*값1*/*:
        */*비교할 값이 값1인 경우 실행될 코드*/*break;
    case */*값2*/*:
        */*비교할 값이 값2인 경우 실행될 코드*/*break;

    */*
    ... 여러개의 case
    */*default:
        */*비교할 값이 위의 모든 값과 다른 경우 실행될 코드*/*break;
}`

### **break**

break구문을 만나면, switch-case 문의 마지막 중괄호(}) 밖으로 빠져나옴.

- break를 사용하지 않으면, switch문에서 빠져나오지 않고 다음 case에 해당하는 코드까지 실행됨.