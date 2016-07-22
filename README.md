NeoUart
=======
Ensure that uart3 is enabled by following this procedure:-   
  cd /boot
  sudo bin2fex script.bin script.fex  
  sudo nano script.fex     
Disable uart0      
  [uart0]    
  uart_used       = 0   
  uart_port       = 0   
  uart_type       = 2   
  uart_tx         = port:PA04<2><1><default><default>   
  uart_rx         = port:PA05<2><1><default><default>    
Enable uart3   
  [uart3]   
  uart_used       = 1   
  uart_port       = 3  
  uart_type       = 2  
  uart_tx         = port:PA13<2><1><default><default>   
  uart_rx         = port:PA14<2><1><default><default>   
  ;uart_rts        = port:PA15<3><1><default><default>   
  ;uart_cts        = port:PA16<3><1><default><default>   
   
Drives a single WS2812B NeoPixel connected to Orange Pi pin PA13 from Image 
 
Syntax: 
 
Accepts pixelspecs in the format [DD]RRGGBB where... 
[DD] is an optional durration in 1/100s of seconds, and 
and RR, GG, and BB are the briness level for red, green, and blue respecively. 
 
All values are hex numbers in the range 00-ff. 
 
Examples of pixelspecs: 
000000=Black, 05FFFF=white for .05s, 800080=50% blue for 1.28s 
 
You can specify one or more pixelspecs on the command line, or run the 
program without parameters and it will read and execute pixelspecs from 
stdin.  
 
Example: 
neouart <demos/disco.nua> 
