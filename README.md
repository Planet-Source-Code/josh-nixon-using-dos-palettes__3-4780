<div align="center">

## ^\!Using DOS Palettes\!^


</div>

### Description

This is a example to show a person how to use more then 16 colors in dos but not all at once.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Josh Nixon](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/josh-nixon.md)
**Level**          |Beginner
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Graphics/ Sound](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics-sound__3-15.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/josh-nixon-using-dos-palettes__3-4780/archive/master.zip)

### API Declarations

```
#include<graphics.h>
#include<dos.h>
```


### Source Code

```
#include<graphics.h>
#include<dos.h>
class Colors
{
 private:
 int graphdriver, graphmode;
 //Palettetype Contains palette information for the current graphics driver
 palettetype pal;//Contains palette information for the current graphics driver
 public:
 void Init_Graphics()
  {
  initgraph(&graphdriver,&graphmode,"..\\BGI\\");
  }
 void Intro();
 Colors::Colors()
 {
  graphdriver = DETECT;
  Init_Graphics();
  //getpalette gets information about the current palette
  getpalette(&pal);//GetPalette demands that a pointer be passed
 }
};
int main()
{
 Colors Colors;
 Colors.Intro();
 return 0;
}
void Colors::Intro()
{
 for(int I = 0; I < 63; I++)
 {
  setbkcolor(1);
  //Defines colors for IBM-8514 graphics card
  setrgbpalette(pal.colors[1],I,I,I);
  delay(100);
 }
 for(I = 63; I > 0; I--)
 {
  settextstyle(DEFAULT_FONT,HORIZ_DIR,6);
  setrgbpalette(pal.colors[2],I,I,I);
  setcolor(2);
   outtextxy(getmaxx()/2-250,getmaxy()/2-20,"Color CRAZY");
   delay(100);
 }//end for
}
```

