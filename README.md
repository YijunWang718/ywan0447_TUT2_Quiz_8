# **Research Report**
## Imaging Technique Inspiration
- *Picture 1*![Image](readmeImages/coding_pt1_1.png)
    [link](https://openprocessing.org/sketch/2211491)
- *Pitcure 2*![Image](readmeImages/coding_pt1_2.png)
    [link]（https://openprocessing.org/sketch/2215414）
- **Reason**
    - Both works divide the canvas into different rectangles, design elements in the rectangles, and change the layout and color combination with each mouse interaction or animation. 
    
    - I think this makes the picture more organized while changing.
## Coding Technique Exploration
- 
- **Reason**
1. 两个作品都使用了数组来确定矩形布局
    - 图片1使用了
```
async function setup() {
  let canvasWidth = 1800;
  let canvasHeight = 1200;

  gridFormats = [
    { x: 3, y: 2 },
    { x: 6, y: 4 },
    { x: 9, y: 6 },
    { x: 18, y: 12 }
  ];

  if (windowHeight > windowWidth) {
    canvasWidth = 1200;
    canvasHeight = 1800;

    gridFormats = [
      { x: 2, y: 3 },
      { x: 4, y: 6 },
      { x: 6, y: 9 },
      { x: 12, y: 18 }
    ];
  }
}
  createCanvas(canvasWidth, canvasHeight);
```
and
```
 let newLayer = new ShapeLayer(nowGrid.x, nowGrid.y, fillRatio, 2, offsetX, offsetY);
```
来生成固定变换的布局。

2. 图片2在建立class时增加了this.t根据this.t的不同赋值与if条件在矩形内部成不同的图案，并且增添了this.t===0来处理画布空白的情况。
```
    class Block {
    constructor(x, y, w, h, c) {
        this.x = x;
        this.y = y;
        this.w = w;
        this.h = h;
        this.c = c;
        this.t = 0; // t < 0 => can be subdivided
        this.p = {}; // empty params for type
    }

    show() {
        push();
        fill(this.c);
        rect(this.x, this.y, this.w, this.h);

        // vertical stripe
        if (this.t === 1) {
        const s = this.w - 4 * sw;
        const n = ~~(this.h / this.w);
        const d = fract(this.h / this.w) * this.w * 0.5;
        const c1 = noiseA(palette, this.x * this.y);
        const c2 = noiseA(palette, this.x + this.y);
                const f = (~~(this.x + this.y) % 2) ? circle : rect;
                rectMode(CENTER);
        for (let i = 0; i < n; i++) {
            fill(c1);
            f(this.x + this.w * 0.5, d + this.y + this.w * (i + 0.5), s);
            if (s > 8 * sw) {
            fill(c2);
            f(
                this.x + this.w * 0.5,
                d + this.y + this.w * (i + 0.5),
                s * 0.5
            );
            }
        }
        }
    }
        if(this,t===2){}
        if(this.t===3){}
        if(debug&&this.t===0){}
    }
```

      