<div align="center">

## movcar


</div>

### Description

applet with multithreading..........
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dilip\_ras](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dilip-ras.md)
**Level**          |Beginner
**User Rating**    |4.0 (8 globes from 2 users)
**Compatibility**  |Java \(JDK 1\.5\)
**Category**       |[Applet](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/applet__2-81.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dilip-ras-movcar__2-6080/archive/master.zip)





### Source Code

```
import java.awt.*;
import java.applet.*;
/*<applet code="movcar.class"height=600 width=600></applet>*/
public class movcar extends Applet implements Runnable
{
	Thread t;
	int x=10,y=50;
	public void init()
	{
	  setBackground(Color.pink);
	  setForeground(Color.blue);
	 // System.out.println("hello m init");
		t=new Thread(this);
		t.start();
	}
	public void run()	//control block
	{
	 while(true)
	  {
		x=x+10;
		if(x>980){
			x=10;y=50;
			}
		repaint();
		if(x>250 && x<319)
		{
		  try{
		    Thread.sleep(150);
		   }
	       catch(InterruptedException e){}
	     }
	   else if(x==320)
	    {
	    	try{Thread.sleep(1000);}
	       catch(InterruptedException e){}
	     }
	    else
		{
		try{
		Thread.sleep(100);
		  }
		 catch(InterruptedException e){}
		}
	}
}
public void paint(Graphics g)   //actual code here
{
	//g.drawString("car",x,y);
	g.setColor(Color.red);
	g.fillRect(x,y,100,50);
	g.setColor(Color.yellow);
	g.fillRect(x+100,y+25,25,25);
	g.setColor(Color.black);
	g.fillOval(x+15,y+35,25,25);
	g.fillOval(x+45,y+35,25,25);
	g.fillOval(x+95,y+35,25,25);
	g.setColor(Color.blue);
	g.fillRect(0,110,600,25);
	g.setColor(Color.white);
	g.fillRect(450,50,10,55);
	if(x>250 && x<319)
	{
	g.setColor(Color.yellow);
	//g.fillOval(450,55,12,12);
	}
	else if(x==320)
	{
	  g.setColor(Color.red);
	//  g.fillOval(450,55,12,12);
	}
	else{
	g.setColor(Color.green);
	//g.fillOval(450,55,12,12);
	}
	g.fillOval(450,55,12,12);
}
}
```

