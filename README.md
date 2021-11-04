# coding
void main() {  // Entry point for execution in C program
  int D;
  char data; //Stores characters data
  ANSELA = 0xFF;
  ANSELD=0;   //Configure PORTC pins as digital
  TRISA = 0xFF;
  TRISD=0;
  UART1_Init(9600);  // Initialize UART module at 9600 bps 
  Delay_ms(100);      // Wait for UART module to stabilize 
  UART_Write_Text("HELLO");

  while(1)       //Endless loop
{

  D = ADC_Read(1);  // The MCU will receive the LDR analog signal via RA1 and convert it to digital and save it in variable D */

   if(D > 1400)
   {
   UART1_Write_Text("OPEN"); // For MCU to send data via UART
   UART1_Write(13);
   UART1_Write(10);
   PORTD = 0xFF;
   }
   else
   {
   UART1_Write_Text("CLOSED");
   UART1_Write(13);
   UART1_Write(10);
   PORTD = 0x00; 
   }
  }
  }
