---
title: "jQuery Practice"
description: ""
categories: javascript&jQuery
tags:
date: 2017-11-14
comments : false
---
## 개요
* jQuery를 이용하여 선택된 checkbox의 value를 textarea 영역에 출력한다.
## 소스코드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
<title>Title</title>
</head>
<script
        src="https://code.jquery.com/jquery-3.2.1.js"
        integrity="sha256-DZAnKJ/6XZ9si04Hgrsxu/8s717jcIzLy3oi35EouyE="
        crossorigin="anonymous">
</script>
<script>
    $(document).ready(function(){

        //전체선택 클릭
        $('#selectAll').on('click',function(){
            //모든 checkbox의 checked 속성을 true로 변경하여 전체선택.
            $('body *').prop('checked',true);
        });

        //전체해제 클릭
        $('#deleteAll').on('click',function(){
            //모든 checkbox의 checked 속성을 false로 변경하여 전체선택해제.
            $('body *').prop('checked',false);
        });


        //body태그 후손 중에 클릭 이벤트 발생 시, textarea의 값 변경.
        $('body *').on('click',function(){

            var value= '';
            var array = $('input[type="checkbox"]:checked'); 
            
            $.each(array,function(){
                value+= $(this).val()+'  ';
            });

            $('textarea').html(value);
        });


    });

</script>
<body>
    <button id="selectAll">전체선택</button>
    <button id="deleteAll">전체해제</button><br>
    <input type="checkbox" value="축구">축구</input><br>
    <input type="checkbox" value="야구">야구</input><br>
    <input type="checkbox" value="농구">농구</input><br>
    <input type="checkbox" value="배구">배구</input><br>
    <input type="checkbox" value="탁구">탁구</input><br>
    <input type="checkbox" value="하키">하키</input><br>

<div><textarea cols="60" rows="20"></textarea></div>

</body>
</html>
```
## 실행화면
<iframe src="/src/jQueryEx" width="650px" height="500px">
           <p>Your browser does not support iframes.</p>
 </iframe>