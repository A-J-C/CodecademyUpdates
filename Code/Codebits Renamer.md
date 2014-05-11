This was made by Joah and is a bookmarklet to rename Codebits on Codecademy.
It will only work on the **edit code** page of your own codebit:

```
javascript:((function(){$.ajax({url:"http://www.codecademy.com/projects/"+window.location.href.split("/")[window.location.href.split("/").length-2],dataType:"json",type:"PUT",data:{authentication_token:CCDATA.current_user.authentication_token,codebit:{id:CCDATA.codebits.current.id,name:prompt("What%20name%20would%20you%20like?")}},beforeSend:function(e){e.setRequestHeader("X-Requested-With","XMLHttpRequest");e.setRequestHeader("Accept","*/*");e.setRequestHeader("X-CSRF-Token",csrf_token)},success:function(e){console.log(e);alert("Name%20successfully%20changed.")},error:function(e){console.log(e);alert("An%20error%20occurred%20while%20changing%20the%20name.%20Please%20check%20your%20JS%20Console.")}})})())()
```

Create a new bookmark and edit the 'URL' part copying in the code from above, then click that bookmark when you are on the codebit page you wish to edit.
