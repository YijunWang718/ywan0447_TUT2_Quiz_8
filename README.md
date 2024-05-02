# **Research Report**
## Imaging Technique Inspiration
- *Picture 1*![Image](readmeImages/coding_pt1_1.png)
- *Picture 2*![Image](readmeImages/coding_pt1_2.png)
- [link](https://openprocessing.org/sketch/2211491)

- **Reason**
    1. The animation in this work is not updated according to the draw function, and it will stay for a while after generating a new image and then change. 
    2. I think this helps to control the animation rendering without device interaction, making each part of the scene present rhythmically rather than refreshing at any time.


## Coding Technique Exploration
- ![Image](readmeImages/coding_pt2_1.png)
    - [code link](https://p5js.org/zh-Hans/reference/#/p5/millis)
- ![Image](readmeImages/coding_pt2_2.png)
    - [code link](https://stackoverflow.com/questions/67221313/how-to-wait-in-p5-js)

- **Reason**
   - Although the original image animation is generated by async/await functions, it is a bit too complicated for me. 
   - Maybe a foor loop and if statements can also be used to simply draw different stages of the animation and reset the screen according to the state of millis(). 
   - For example, call the different functions to draw the image every 1000 seconds. Keeping all elements still in a certain part to achieve a short stagnation

   