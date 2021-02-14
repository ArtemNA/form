Form for auto search TFT wtb msg in discord(BROWSER ONLY)

go to https://artemna.github.io/form/index.html and fill the form (first 10 input text area for input and last one for output result for u)



then open one tab with discord.com/app and open channel u want, open console (cntr+shift+i) and paste next code with the replacement of the line you received from the form(second line)

```
var last=[]
var want=[] //<===REPLACE IT
function notifyMe(x) {
  // Let's check if the browser supports notifications
  if (!("Notification" in window)) {
    alert("This browser does not support desktop notification");
  }

  // Let's check if the user is okay to get some notification
  else if (Notification.permission === "granted") {
    // If it's okay let's create a notification
    var notification = new Notification(x);
  }

  // Otherwise, we need to ask the user for permission
  // Note, Chrome does not implement the permission static property
  // So we have to check for NOT 'denied' instead of 'default'
  else if (Notification.permission !== 'denied') {
    Notification.requestPermission(function (permission) {

      // Whatever the user answers, we make sure we store the information
      if(!('permission' in Notification)) {
        Notification.permission = permission;
      }

      // If the user is okay, let's create a notification
      if (permission === "granted") {
        var notification = new Notification(x);
      }
    });
  } else {
    alert(`Permission is ${Notification.permission}`);
  }
}

function myTriger(){
	var a = [];
	var b
	for (var j = 0; j < want.length; j++) {
	a[j] = new Array();
}
        var test=document.getElementsByClassName("markup-2BOw-j messageContent-2qWWxC");//test is not target element
        //console.log(test);//HTMLCollection[1]

for (var j = 0; j < want.length; j++) {
for (var i = 0; i <test.length ; i++) {

        var testTarget=document.getElementsByClassName("markup-2BOw-j messageContent-2qWWxC")[i].innerHTML;//hear , this element is target
       
       

        if(testTarget.includes(want[j])){
        //console.save(testTarget);//<p class="test">hello word2</p>
        a[j].push(testTarget);
        console.log(a[j][i])
        }
    }
    }
for (var j = 0; j < want.length; j++) {
	var s = a[j].length;
    b=a[j][s-1];
console.log(b);
    if(last[j]!=b && b!=null){   
    last[j]=b;
notifyMe(b);
}
}


//console.save(a,'log.txt');
}

myTriger();

setInterval(function(){
    myTriger()
}, 15000)

```
Enjoy!
