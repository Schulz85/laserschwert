# laserschwert
#define numberOfButtons 3

#include <avr/io.h>
#include <util/delay.h>
#include <avr/interrupt.h>
#include "buttonPress.h"
#include <stdlib.h>			// die beinhaltet die rand funktion

int i;

int main(void)
{
DDRB = 0b00000111;
DDRA = 0b00000000;
PORTA = 0b00000111;


i=4;

while(1)
{
if (ButtonPressed(0, PINA, 0, 200))
{
PORTB = 0b00000001;
_delay_ms(600);
PORTB = 0b00000000;
}
if (ButtonPressed(1, PINA, 1, 200)) //HIER BRAUCHE ICH DEN ZUFALLSGENERATOR

r = rand() % 7 + 4; // hier bekommst du nun für r von 4 bis 7 eine zufallsvariable

{
if (i == 8) i=4;
PORTB |= 1<<i;
_delay_ms(600);
PORTB = 0b00000000;
i = i+1;

}

}
}
