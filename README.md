# Jumper

Членови на тимот: 
- Трајче Ифтимов 173252
- Игор Летников 172060
 
1.0 Опис на апликацијата
- Апликацијата е идеја од играта Супер Марио, но овој пат те следат 2 enemy, додека паѓаат бомби од небо и летаат ракети од страна. Исто така паѓаат и парички од небо. 
Ваша цел е да собирате парички и да останете што е можно подолго во играта.<br />
![](Images/Gameplay1.png)<br />
![](Images/Gameplay2.png)<br />
 
2.0 Упатство за користењe
- На почеток на апликацијата добиваме почетно мени кои ги има следните опции:
![](Images/MainMenu.png)<br />
2.1 Start - при клик на ова копче се пренасочува нова форма кадешто започнува играта<br />
2.2 Instructions - добиваме поглед кој ни објаснува како работи играта односно движењето е овозможено со стрелките лево-десно додека скокањето е овозможено со space. 
Правилата на играта се следни: допир на enemy или допир на бомба или допир на ракета играта завршува, додека секое одбегнување на бомба добивате еден поен или секое фаќање на паричка добивате десет поени.<br />
![](Images/Instructions.png)<br />
2.3 Exit - копче за излегување од апликацијата
 
3.0 Имплементација
 
Движењето или влезот од тестатура е овозможен со KeyDown/KeyUp евентите.
 
private void Form1_KeyDown(object sender, KeyEventArgs e)
        {
            switch (e.KeyCode)
            {
                case Keys.Left:
                    Player_Left = true;
                    break;
                case Keys.Right:
                    Player_Right = true;
                    break;
            }
        }
 
Гравитацијата е организирана со помош на timer на следниот начин 
 
Код кој ни го овозможува скокањето нагоре:
 
private void timer_Jump_Tick(object sender, EventArgs e)
      {
          if (Force > 0)
          {
              if (Collision_Bottom(pb_Player))
              {
                  Force = 0;
              }
              else
              {
                  Force--;
                  pb_Player.Top -= Speed_Jump;
              }
          }
          else
          {
              Player_Jump = false;
          }
      }
 
Код за паѓањето на играчот
 
private void timer_Jump_Tick(object sender, EventArgs e)
      {
          if (Force > 0)
          {
              if (Collision_Bottom(pb_Player))
              {
                  Force = 0;
              }
              else
              {
                  Force--;
                  pb_Player.Top -= Speed_Jump;
              }
          }
          else
          {
              Player_Jump = false;
          }
      }
 
Дополнително имаме код кој ги користи компонентите PictureBox и во позадина се грижи за Collision помеѓу играчот и останатите објекти.
 
 
4.0 За изработка користевме туторијали и делови кодови кои што ни помогнаа во изработка на апликацијата. Ресурсите, сликите кои се користени во апликацијата се превземени од интернет.
Референца кон туториал:
https://www.youtube.com/watch?v=rQBHwdEEL9I&ab_channel=MooICT 
