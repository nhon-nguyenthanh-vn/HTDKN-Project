/**
														HEADER VALUE	
	STX 													49								
	ACK 													50								
	NCK 													51								
	ETX 													57									
	** SEND FRAME 	
		* COMMAND 	: 	 
		49  	 44      48(49)    44     		48(49)  		 44    			 MSB	 		 44         LSB			   44				57 		 										(--11 byte--)
		STX  		,  		MOV(POS)  	,  		(MODE ENCODER)  	,     	SETPOINT  		,    		SETPOINT			, 			ETX	
		
		* ECHO COMMAND: 
		49  	 44      48(49)    44     		48(49)  		 44    			 MSB	 		 44         LSB			   44				50			 44			   57 		(--13 byte--)
		STX  		,  		MOV(POS)  	,  		(MODE ENCODER)  	,     	SETPOINT  		,    		SETPOINT			,				ACK				, 			ETX	
		
		* DATA: 
		49  	 44     				   44                      44										 44									44					48			 44			   57			(--13 byte--)
		STX  		,  		DATA[3]  		,  				DATA[2]  			,     	DATA[1]     	,      	DATA[0]     	,   		ZERO			,				ETX	
		
	** UART PIN:				PA2 	- 	TX 	, 	PA3 	- 		RX
	** CONTROL MODE : 	POS 	- 	48 	, 	MOV 	- 		49
	** ENCODER MODE :  	X1 		- 	48	, 	X4 		- 	 	49
	** PWM PIN:					PD12  - 	CH1 , 	PD13	- 		CH2
	** ENCODER PIN:			PA0		-		EXTI0,	PA1		-			EXTI1 
  ** GND should be commoned for accuracy encoder reading
	*****/
  
