<div align="center">

## An 100 Year Calender\(with better GUI\)


</div>

### Description

One can get an overview of Selected Month &amp; Year.

with leap year details.
 
### More Info
 
There is no input required to run the Application.

No Nothing.(I mean you must be A Java Programmer)

After running the application you just select the monyh &amp; year.

As i wish , There are No Side effects of Application.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Pankaj  S\.Ganorkar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/pankaj-s-ganorkar.md)
**Level**          |Intermediate
**User Rating**    |4.4 (31 globes from 7 users)
**Compatibility**  |Java \(JDK 1\.5\)
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__2-64.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/pankaj-s-ganorkar-an-100-year-calender-with-better-gui__2-5899/archive/master.zip)





### Source Code

```
// TO DISPLAY CALENDER OF SPECIFIED MONTH & YEAR.
// Developed By :- Pankaj Ganorkar.
// Supported By :- Deepak Ganorkar.
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class Calender extends JFrame implements ActionListener , ItemListener
 {
 JButton jb[] = new JButton[42];
 static JComboBox monthChoice = new JComboBox();
 static JComboBox yearChoice = new JComboBox();
 JLabel days[] = new JLabel[7];
 JLabel l[] = new JLabel[5];
 int year,month,flag,rem,h;
 char ch;
 char Years[] = {'A','B','C','K','F','G','A','I','D','E','F','N','B',
  'C','D','L','G','A','B','J','E','F','G','H','C',
  'D','E','M','A','B','C','K','F','G','A','I','D','E',
  'F','N','B','C','D','L','G','A','B','J','E','F',
  'G','H','C','D','E','M','A','B','C','K','F','G','A',
  'I','D','E','F','N','B','C','D','L','G','A','B',
  'J','E','F','G','H','C','D','E','M','A','B','C','K',
  'F','G','A','I','D','E','F','N','B','C','D','E'};
 int Months[][]={{1,4,4,7,2,5,7,3,6,1,4,6},
         {2,5,5,1,3,6,1,4,7,2,5,7},
         {3,6,6,2,4,7,2,5,1,3,6,1},
         {4,7,7,3,5,1,3,6,2,4,7,2},
         {5,1,1,4,6,2,4,7,3,5,1,3},
         {6,2,2,5,7,3,5,1,4,6,2,4},
         {7,3,3,6,1,4,6,2,5,7,3,5},
         {1,4,5,1,3,6,1,4,7,2,5,7},
         {2,5,6,2,4,7,2,5,1,3,6,1},
         {3,6,7,3,5,1,3,6,2,4,7,2},
         {4,7,1,4,6,2,4,7,3,5,1,3},
         {5,1,2,5,7,3,5,1,4,6,2,4},
         {6,2,3,6,1,4,6,2,5,7,3,5},
         {7,3,4,7,2,5,7,3,6,1,4,6}};
  static
 {
   monthChoice.addItem("JAN");
   monthChoice.addItem("FEB");
   monthChoice.addItem("MAR");
   monthChoice.addItem("APR");
   monthChoice.addItem("MAY");
   monthChoice.addItem("JUN");
   monthChoice.addItem("JUL");
   monthChoice.addItem("AUG");
   monthChoice.addItem("SEP");
   monthChoice.addItem("OCT");
   monthChoice.addItem("NOV");
   monthChoice.addItem("DEC");
 }
  public Calender()
  {
   setVisible(true);
   setLayout(null);
   setSize(500,400);
  // center screen
  setLocation((Toolkit.getDefaultToolkit().getScreenSize().width
						- getWidth())/2,
		  		(Toolkit.getDefaultToolkit().getScreenSize().height
		  			- getHeight())/2);
  // setBounds(150,150,500,400);
   setForeground(Color.red);
   setTitle("Calender Box");
   Font F = new Font("Dialog",Font.BOLD,16);
   setFont(F);
  for(int i=0;i<42;i++)
   {
	jb[i] = new JButton();	add(jb[i]);
    jb[i].addActionListener(this);
   }
   for(int i=0;i<5;i++)
   {
	l[i] = new JLabel();
	l[i].setFont(F);   add(l[i]);
   }
   l[0].setText("Month");
   l[1].setText("Year");
   l[0].setBounds(25,90,150,30);
   l[1].setBounds(25,170,150,30);
   l[2].setBounds(150,330,250,30);
   l[3].setText("Calender");
   l[3].setBounds(175,10,150,30);
   l[3].setFont(new Font("Georgia",Font.BOLD,26));
   l[3].setForeground(Color.RED);
   add(monthChoice);
   add(yearChoice);
   monthChoice.setBounds(25,120,75,30);
   yearChoice.setBounds(25,200,75,30);
   monthChoice.addItemListener(this);
   yearChoice.addItemListener(this);
   for(int i=1;i<=100;i++)
   {
    yearChoice.addItem(2000+i);
   }
   for(int i=0;i<7;i++)
   {
    int x1=130;
	days[i] = new JLabel();
	days[i].setFont(F);   add(days[i]);
    days[i].setBounds(x1+(i*50),50,50,30);
   }
   days[0].setText("MON");
   days[1].setText("TUE");
   days[2].setText("WED");
   days[3].setText("THU");
   days[4].setText("FRI");
   days[5].setText("SAT");
   days[6].setText("SUN");
   int k=0;
   for(int i=0;i<6;i++)
   {
    int y=80;
    for(int j=0;j<7;j++)
    {  int x=130;
      jb[k].setBounds((x+(j*50)),y+(i*40),50,40);
      k++;
    }
   }
  }
//==============================================================================
  public void Monday(int X)
  {
  int day=1;
  for(int i=0;i<31;i++)
   {
    jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
  public void Tuesday(int X)
  {
  int day=1;
  for(int i=1;i<32;i++)
   {
	jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
  public void Wednesday(int X)
  {
    int day=1;
  for(int i=2;i<33;i++)
   {
	jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
  public void Thursday(int X)
  {
    int day=1;
  for(int i=3;i<34;i++)
   {
    jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
  }
  }
  public void Friday(int X)
  {
    int day=1;
  for(int i=4;i<35;i++)
   {
    jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
  public void Saturday(int X)
  {
  int day=1;
  for(int i=5;i<36;i++)
   {
    jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
  public void Sunday(int X)
  {
  int day=1;
  for(int i=6;i<37;i++)
   {
    jb[i].setText(""+day);
    day++;
    if(day==(X+1))
      break;
   }
  }
//==============================================================================
  public void drawCalender()
   {
   year=(yearChoice.getSelectedIndex());
   System.out.println(yearChoice.getSelectedItem());
   System.out.println(yearChoice.getSelectedIndex());
   System.out.println(monthChoice.getSelectedItem());
   System.out.println(monthChoice.getSelectedIndex());
   month=(monthChoice.getSelectedIndex());
   ch=Years[year];
   int L=0;
   for(char i='A';i!=ch;i++)
   { L++;
   }
    System.out.println(""+ch+L);
	if(month==0||month==2||month==4||month==6||month==7||month==9||month==11)
	{
       flag=4;
      System.out.println(flag);
	}
	else
     { if(month==1)
       {
        rem=(year+1)%4;
        if(rem==0)
        {
          flag=2;
          System.out.println(flag);
          l[2].setText("THIS IS A LEAP YEAR");
         }
         else
         {
          flag=1;
          System.out.println(flag);
         }
       }
      else
        {
          flag=3;
          System.out.println(flag);
         }
     }
//==============================================================================
   int Day= Months[L][month];
   switch(Day)
     {
     case 1:
     {
        switch(flag)
      {
      case 1:
      {
        Monday(28);break;
      }
      case 2:
      {
        Monday(29);break;
      }
      case 3:
      {
        Monday(30);break;
      }
      case 4:
      {
        Monday(31);break;
      }
      default :
      {
         break;
      }
      }
        break;
     }
     case 2:
     {
         switch(flag)
        {
          case 1:
          {
            Tuesday(28); break;
          }
          case 2:
          {
            Tuesday(29); break;
          }
          case 3:
          {
            Tuesday(30); break;
          }
          case 4:
          {
            Tuesday(31); break;
          }
          default :
          {
            break;
          }
        }
         break;
      }
      case 3:
      {
         switch(flag)
      {
        case 1:
        {
          Wednesday(28); break;
        }
        case 2:
        {
          Wednesday(29); break;
        }
        case 3:
        {
          Wednesday(30); break;
        }
        case 4:
        {
          Wednesday(31); break;
        }
        default:
        {
          break;
        }
      }
         break;
      }
      case 4:
      {
        switch(flag)
     {
      case 1:
      {
        Thursday(28); break;
      }
      case 2:
      {
        Thursday(29); break;
      }
      case 3:
      {
        Thursday(30); break;
      }
      case 4:
      {
        Thursday(31); break;
      }
      default:
      {
        break;
      }
     }
        break;
      }
      case 5:
      {
        switch(flag)
	 {
      case 1:
      {
        Friday(28); break;
      }
      case 2:
      {
        Friday(29); break;
      }
      case 3:
      {
        System.out.println("sunday31");
        Friday(30); break;
      }
      case 4:
      {
        Friday(31); break;
      }
      default:
      {
        break;
      }
     }
        break;
      }
      case 6:
      {
         switch(flag)
	  {
      case 1:
      {
        Saturday(28); break;
      }
      case 2:
      {
        Saturday(29); break;
      }
      case 3:
      {
        Saturday(30); break;
      }
      case 4:
      {
        Saturday(31); break;
      }
      default:
      {
        break;
      }
      }
         break;
      }
      case 7:
      {
        switch(flag)
	 {
      case 1:
      {
        Sunday(28); break;
      }
      case 2:
      {
        Sunday(29); break;
      }
      case 3:
      {
        Sunday(30); break;
      }
      case 4:
      {
        Sunday(31); break;
      }
      default:
      {
        break;
      }
     }
        break;
    }
    default :
    {
     break;
    }
   }
  }
//==============================================================================
 public void actionPerformed(ActionEvent e)
  {
//    String arg = e.getActionCommand();
//    if(arg.equals("OK"))
//    { setVisible(false);  }
  }
 public void itemStateChanged(ItemEvent ie)
  {
   for(int i=0;i<42;i++)
    {jb[i].setText("");}
    l[2].setText("");
    drawCalender();
  }
 public static void main(String[] args)
 {
  new Calender();
 }
}
```

