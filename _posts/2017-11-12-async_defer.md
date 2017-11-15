---
title: "script의 async & defer 속성"
description: ""
categories: javascript&jQuery
tags: 
date: 2017-11-12
comments : false
---
## 일반적인 실행
일반적인 스크립트 태그의 경우 html 파싱 중 스크립트 태그를 읽게 되면 스크립트를 다운받고 실행할 때까지 html 파싱을 멈춘다.<br>
이 경우에 html 태그의  앞부분에 스크립트 태그를 배치하게되면(특히 \<head> 내에) 페이지 렌더링이 시작되기도 전에 스크립트를 다운로드하고 실행하는데 시간을 할애하게된다.
이는 사용자 입장에서 봤을때, 스크립트가 다운되는 동안 빈페이지를 보고 있어야 한다.<br>
이를 해결하기 위해서 HTML5에서 async 속성과 defer 속성이 추가되었다.
![Smithsonian Image](/postImg/normal.png)
## async
async 속성은 브라우저에 스크립트 파일이 비동기적으로 실행될 수 있음을 나타내기 위해 사용한다.
HTML 파싱과 동시에 스크립트 다운로드가 진행되며, 다운로드가 완료되는 순간 HTML 파싱을 잠시 멈춘 후 스크립트를 실행한다.<br>
따라서 실행의 순서가 다운로드 완료 시점의 결정되므로 실행 순서가 중요한 스크립트들에 async를 사용할 때는 유의해야 한다.<br>
`HTML5 spec에 async=false 속성 지정시 호출 순서대로 실행되도록 추가되었다고 한다. (default : true)`
![Smithsonian Image](/postImg/async.png)
```javascript
<script async src="https://maps.googleapis.com"></script>
```
## defer
defer속성은 HTML 구문 분석이 실행되는 동안 파일을 다운로드 할 수있지만, HTML 구문 분석이 완료되기 전에 스크립트 다운로드가 완료 되더라도 구문 분석이 완료 될 때까지 스크립트는 실행되지 않는다. `또한 async 속성과 다르 호출된 순서대로 실행된다.`
![Smithsonian Image](/postImg/defer.png)
```javascript
<script defer src="https://maps.googleapis.com"></script>
```
                                                                                                                                     

