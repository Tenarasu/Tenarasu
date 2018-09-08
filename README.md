 Tenarasu
/*simple c program  using LED Blinking */
#include<htc.h>
void delay();
int main()
{
    TRISB=0;
    while(1)
    {
    PORTB=0XFF;
    delay();
    PORTB=0X00;
    delay();
    }
}
void delay()//using delay for timer1 delay 
{
   T1CKPS1=1;       // Select prescalars using timer calculation
   T1CKPS0=1;
   TMR1CS=0;       // Timer1 clock source select internal clock 
   TMR1H=0X0B;     // Timer1 high value 
   TMR1L=0XDB;     // Timer1 low value   and timer is 100ms delay values
   TMR1ON=1;
   while(!TMR1IF); // Timer1 interrupt flag
   TMR1IF=0;
}
