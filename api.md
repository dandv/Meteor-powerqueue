#PowerQueue
This package contains a small api
Does `markdown` __work__ here?
* Okay
* Yep

## <a name="PowerQueue"></a>new PowerQueue([options])&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##
Creates an instance of a power queue 
[Check out demo](http://power-queue-test.meteor.com/)

<u><b>Arguments</b></u>

* __options__ *{object}*
  Settings
    - __filo__ *{boolean}*    (Default = false)
Make it a first in last out queue
    - __isPaused__ *{boolean}*    (Default = false)
Set queue paused
    - __autostart__ *{boolean}*    (Default = true)
May adding a task start the queue
    - __name__ *{string}*    (Default = "Queue")
Name of the queue
    - __maxProcessing__ *{number}*    (Default = 1)
Limit of simultanous running tasks
    - __maxFailures__ *{number}*    (Default = 5)
Limit retries of failed tasks
    - __text__ *{ number | string }*    (Default = ' ')
Hmm, comment

-
After text

> ```PowerQueue = function(options) { ...``` [power-queue.js:22](power-queue.js#L22)

## <a name="PowerQueue.onEnded"></a>PowerQueue.onEnded&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##
Is called when queue is ended

> ```self.onEnded = options && options.onEnded || function() { ...``` [power-queue.js:64](power-queue.js#L64)

## <a name="PowerQueue.onAutostart"></a>PowerQueue.onAutostart&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##
Is called when queue is auto started

> ```self.onAutostart = options && options.onAutostart || function() { ...``` [power-queue.js:69](power-queue.js#L69)

## <a name="PowerQueue.length"></a>PowerQueue.length()&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##

__Returns__  *{number}*  <u>is reactive</u>
Number of tasks left in queue to be processed

> ```self.length = invocations.length;``` [power-queue.js:75](power-queue.js#L75)

## <a name="PowerQueue.progress"></a>PowerQueue.progress()&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##

__Returns__  *{number}*
0 .. 100 % Indicates the status of the queue

> ```self.progress = function() { ...``` [power-queue.js:80](power-queue.js#L80)

## <a name="PowerQueue.usage"></a>PowerQueue.usage()&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##

__Returns__  *{number}*
0 .. 100 % Indicates ressource usage of the queue

> ```self.usage = function() { ...``` [power-queue.js:91](power-queue.js#L91)

## <a name="PowerQueue.total"></a>PowerQueue.total()&nbsp;&nbsp;<sub><i>Anywhere</i></sub> ##

__Returns__  *{number}*
The total number of tasks added to this queue

> ```self.total = _maxLength.get;``` [power-queue.js:98](power-queue.js#L98)

-
If the task handler throws an error then add it to the queue again
we allow this for a max of _maxFailures

-
This could be overwritten the data contains the task data and addTask
is a helper for adding the task to the queue
try again: addTask(data);