In this section, we will introduce a concept introduced by Princess Studio.

##### 1. Remaining Time Counter
In any battle in PrincessConnectReDive, you will get a remaining time counter on the top right hand corner next to the pause button.

##### 2. Limit Time
Limit time is essentially the time given for a single battle, typically this is 90 seconds for a full battle. Carryover in the clan battle feature get discounted from the time used in the original hit.

##### 3. Render Frame
In the code base of PrincessConnectReDive, minimum increment of time is recorded by `FrameCount`. `FrameCount` is essentially the frames progressed since battle started. To differentiate from `Logic Frame`, Princess Studio named `FrameCount` as `Render Frame`.

##### 4. Logic Frame
While `Render Frame` is the frames progressed since battle started, it is also important to note that this `FrameCount` will include any cut-in scene played upon execution of union burst. This makes communication of precise union burst execution time trivial.

###### 4.1 Frame Rate
```
1 Second = 60 Frames
```

###### 4.2 Cut-In
A special feature in this game is that, in general, cut-in scene in PrincessConnectReDive do not consume `Limit Time`. Therefore, the more union bursts executed in the same `Limit Time` the more `Render Frame` it will progress. Note, certain characters holds union bursts in which part of the execution time consumes `Limit Time`.

###### 4.3 Logic Frame
Since `Render Frame` includes frames progressed when `Limit Time` is actually not progressing. Princess Studio introduced a new concept named `Logic Frame`. `Logic Frame` is essentially the frames progressed when `Limit Time` is actually being consumed. Therefore, the total frame in a battle with 90 seconds of `Limit Time` is as followed:
```
90 Seconds * 60 Frames / Seconds = 5400 Frames
```
A battle of 90 seconds will start from frame `0` and end in frame `5399`.