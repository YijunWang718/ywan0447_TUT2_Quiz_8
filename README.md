# **Research Report**
## Imaging Technique Inspiration
- *Picture 1*![Image](readmeImages/coding_pt1_1.png)
    [link](https://openprocessing.org/sketch/2211491)

- **Reason**
    - I noticed that the animation in this work is not updated according to the refresh frequency of the draw function like in js works, but it will stay for a while after generating a new image and then change. At the same time, the screen elements can change according to the mouse position.

## Coding Technique Exploration
- ![Image](readmeImages/coding_pt2_1.png)
    [code link](https://p5js.org/zh-Hans/reference/#/p5/millis)
- ![Image](readmeImages/coding_pt2_2.png)
    [introduction link](https://stackoverflow.com/questions/67221313/how-to-wait-in-p5-js)

- **Reason**
   - Although the original image animation is generated by async/await functions, it is a bit too complicated for me. Maybe a foor loop and if statements can be used to simply draw different stages of the animation and reset the screen according to the state of millis(). 
   - For example, call a different function to draw the image every 1000 seconds.