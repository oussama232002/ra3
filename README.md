# ra3
rafdfdsfdsfsdfsdfsffsdfsdfs
/********************************************************************************************************************
--------------------------------------------------------------------------------------------------------------------

███╗   ██╗ █████╗ ██╗███████╗     █████╗ ██╗      ██████╗ ████████╗ █████╗ ██╗██████╗ ██╗
████╗  ██║██╔══██╗██║██╔════╝    ██╔══██╗██║     ██╔═══██╗╚══██╔══╝██╔══██╗██║██╔══██╗██║
██╔██╗ ██║███████║██║█████╗      ███████║██║     ██║   ██║   ██║   ███████║██║██████╔╝██║
██║╚██╗██║██╔══██║██║██╔══╝      ██╔══██║██║     ██║   ██║   ██║   ██╔══██║██║██╔══██╗██║
██║ ╚████║██║  ██║██║██║         ██║  ██║███████╗╚██████╔╝   ██║   ██║  ██║██║██████╔╝██║
╚═╝  ╚═══╝╚═╝  ╚═╝╚═╝╚═╝         ╚═╝  ╚═╝╚══════╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚═╝╚═════╝ ╚═╝
********************************************************************************************************************
--------------------------------------------------------------------------------------------------------------------

███████  ██████  ██      ██████  ██ ███████ ██████      ███████  ██████  
██      ██    ██ ██      ██   ██ ██ ██      ██   ██          ██ ██       
███████ ██    ██ ██      ██   ██ ██ █████   ██████          ██  ███████  
     ██ ██    ██ ██      ██   ██ ██ ██      ██   ██        ██   ██    ██ 
███████  ██████  ███████ ██████  ██ ███████ ██   ██        ██    ██████  
                                                                         
********************************************************************************************************************
--------------------------------------------------------------------------------------------------------------------


////////////////////////////////////////////////////////////////
 
 
 
للتواصصل معي 
   
0 5 4 7 0 7 7 5 4 1
 

////////////////////////////////////////////////////////////////


OVERWATCH 2

 شخصيه سوولجر ميزه الانتي ريكول فقط 
موزون بقيمه 30 

ظبط االنتي ريكول - الثبات - 
 
1- L2+ستارت
2- NAIF AR
زر اكس - X- 3
4- NAIF AR VERT 1 RY 
************************
************************
سهم فوق زيادة بمقدار +1 
NAIF AR VERT 1 RY = فوق تحت 

سهم تحت ينقص بمقدار -1
NAIF AR VERT 1 RX = يمين يسار 
 ************************
 ************************

اذا السلاح  يطلع لفوق زود العدد كذا مره
واذا ينزل تحت نقص الرق
 
 */
const uint8 FontSize [][] = {{ 7, 10, 18 },{ 11, 18, 11 },{ 16, 26, 7 }};
const uint8 FontDigits [] = {48,49,50,51,52,53,54,55,56,57};
                                                                                                                                                                                                                                                                 const string MiscString [] = {"MOD","ON","OFF","Naif SOLDIER-76","0547077541","GPC Slot:","Enabled","Disabled","Mod Toggle On/Off"};
const string ModToggle [] = {""  , "   NAIF AR" };
                                                                                                                                                                                                                                                                  const string ModValue [] = {""   , "NAIF AR VERT 1 RY" , "NAIF AR VERT 1 RX" };
const int16 ModDigitMin [] = {  0  , 1 , -50};
const int16 ModDigitMax [] = {  0  , 100 , 50};
const int16 ModDigitInc [] = {  0  , 1 , 1};

define Fire     = PS4_R2;
define Ads      = PS4_L2;
define Lethal   = PS4_R1;
define Tactical = PS4_L1;
define Switch   = PS4_TRIANGLE;
define Reload   = PS4_SQUARE;
define Jump     = PS4_CROSS;
define Crouch   = PS4_CIRCLE;
define Melee    = PS4_R3;
define Sprint   = PS4_L3;
define Ping     = PS4_UP;
define Up       = PS4_UP;
define Down     = PS4_DOWN;
define Left     = PS4_LEFT;
define Right    = PS4_RIGHT;
define AimX     = PS4_RX;
define AimY     = PS4_RY;
define Strafe   = PS4_LX;
define Walk     = PS4_LY;
define PY       = POLAR_RY;
define PX       = POLAR_RX;
define PS       = POLAR_RS;
define On       = TRUE;
define Off      = FALSE;
/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~.
(                    Menu Buttons                    )
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-*
*/
define MenuEnterHold   = PS4_L2;
define MenuEnterPress  = PS4_OPTIONS;
define MenuExitPress   = PS4_CIRCLE;
define ChangeMenuPress = PS4_CROSS;

//Show Current Slot Info Buttons;
define FindSlotHold    = PS4_R3;
define FindSlotPress   = PS4_LEFT;
/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~.
(                 Script Variables                   )
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-*
*/
define TimeoutLimit  = 1;
define TimeoutLimitM = 20000;
define IndexMinSwitches = 1;
define IndexMaxSwitches = 1;
define IndexMinValues   = 1;
define IndexMaxValues   = 2;

int Position,Update,MenuTimeout,Count,MainMenu,ModIndex,MenuValues,MenuSwitch,NumX,NumY,NumS,Clear,Shunt,VibA,VibB;
int Number = 1,Slot = 20000;

int ScrollTime,ScrollWait,ScrollLine,ScrollIndex,ScrollChar;
int ScrollSpeed =  70;
int ScrollDelay = 950;
int ScrollX     =   8;
int ScrollY     =  50;

int SmartRumble,AntirecoilStrength;
int Output;

/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~.
(            Anti Recoil Hip Fire/Settings           )
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-*
*/
// Anti Recoil Hip Fire
define TaylorARHip      =  On;
// Anti Recoil Inverted
define InvertedYAxis    = Off;
define TaylorARRumble   = Off;

/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                Mod Values/Times                    ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 
int ModDigit;
int TaylorAR1RY      = 30;
int TaylorAR1RX      = 0;
/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                   Mod Toggles                      ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 
int ModSwitch;
int TaylorAntiRecoil  =  On;

/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                       Init                         ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 

init {
    combo_run(Boot);
}

/*
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                       Main                         ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 

main {


        if (TaylorAntiRecoil) {
                   
            if (TaylorARHip && get_ival(Fire) || get_ival(Ads) && get_ival(Fire) && !TaylorARHip) { 
                    
                if (!get_rumble(RUMBLE_A) || !get_rumble(RUMBLE_B))  { 
                
                    if (InvertedYAxis)
                    
                        set_val(PY,DoGzGetPolar(get_val(PY),inv(TaylorAR1RY) * 327));
                    else 
                    
                        set_val(PY,DoGzGetPolar(get_val(PY),TaylorAR1RY * 327)); 
                    
                } else {
                    
                    SmartRumble = get_rumble(RumbleToUse());
                            
                    if (SmartRumble > 10 && SmartRumble < 90) {
                        
                        AntirecoilStrength = TaylorAR1RY + SmartRumble / 4;
                        SmartRumble = 0; 
                    }
                    
                    if (TaylorARRumble) {
                    
                        if (InvertedYAxis)                        
                        
                            set_val(PY,DoGzGetPolar(get_val(PY),inv(AntirecoilStrength) * 327)); 
                        
                        else
                        
                            set_val(PY,DoGzGetPolar(get_val(PY),AntirecoilStrength * 327)); 
                        
                        set_val(PX,DoGzGetPolar(get_val(PX),TaylorAR1RX)); 
                    
                    } else {     
                        
                        if (InvertedYAxis)
                        
                            set_val(PY,DoGzGetPolar(get_val(PY),inv(TaylorAR1RY) * 327)); 
                        
                        else
                        
                            set_val(PY,DoGzGetPolar(get_val(PY),inv(TaylorAR1RY) * 327));                        
                        
                        set_val(PX,DoGzGetPolar(get_val(PX),TaylorAR1RX * 327));                     
                    }
                    
                    SmartRumble = 0;  
                    AntirecoilStrength = 0;   
                }
            }
        }

    if (!MainMenu && get_ival(MenuEnterHold) && event_press(MenuEnterPress)) {

        Shunt = MenuEnterPress;
        MenuToggle(On,Off,On,On,On);
        VibB = On;
        combo_run(Rumble);
    }

    if (MainMenu) {

        Scroll();
        combo_stop(Boot);
        MenuTimeout += get_rtime();

        if (get_ival(Up) || get_ival(Down) || get_ival(Left) || get_ival(Right) || event_press(ChangeMenuPress)) {

            MenuTimeout = Off;
        }

            if (MenuTimeout >= TimeoutLimitM || event_press(MenuExitPress)) {
            
                if (event_press(MenuExitPress))
                
                    Shunt = MenuExitPress;
                
                MenuToggle(Off,Off,Off,Off,Off);
                VibB = On;
                combo_run(Rumble);
            }

            if (event_press(ChangeMenuPress)) {

                MenuValues = !MenuValues;
                MenuSwitch = !MenuSwitch;
                ModIndex = On;
                Update = On;
            }

        if (MenuValues) {

            ModDigit[ModIndex] = PrintMod(ModDigit[ModIndex],ModDigitMin[ModIndex],ModDigitMax[ModIndex],ModDigitInc[ModIndex],IndexMinValues,IndexMaxValues,ModValue[ModIndex]);
		}

        if (MenuSwitch) {

            ModSwitch[ModIndex] = PrintMod(ModSwitch[ModIndex],Off,On,1,IndexMinSwitches,IndexMaxSwitches,ModToggle[ModIndex]);
		}

				BlockButton(Down); BlockButton(Up); BlockButton(Left); BlockButton(Right); BlockButton(ChangeMenuPress);
	}
 
    if (!MainMenu) { 
        
        if (get_ival(FindSlotHold) && event_press(FindSlotPress)) {
            
            Shunt = FindSlotPress;
            Slot = On;
            combo_run(Boot);
        }
    }

    if (Shunt) {
        
        if (event_release(Shunt)) {
            
            Shunt = Off;
        
        } else {
                set_val(Shunt,Off);
        }
    }
}

/* 
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                   Combos                           ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 

combo Rumble {
    
    if (VibA)
        
        set_rumble(RUMBLE_A,15);
        
    else if (VibB)
            
        set_rumble(RUMBLE_B,15);
    
        wait(250);
        VibA = Off;
        VibB = Off;
        reset_rumble();
}

combo Boot {
        

    if (Slot == 20000)    
        cls_oled(0);
        
        if (Slot) {
            cls_oled(0);
            printf(5,10,0,1,MiscString[3]);
            printf(5,25,0,1,MiscString[4]);
            printf(18,45,0,1,MiscString[5]);
            NumX = 32; NumY = 15; NumS = 0;
            FindDigit(get_slot(),DigitValue(get_slot()));
            Slot = Off;
        }    
        
        wait(20000);
        cls_oled(0);
        Clear = On;
}

/* 
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                   Functions                        ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 

function RumbleToUse() {
    
    if (get_rumble(RUMBLE_A) >= get_rumble(RUMBLE_B)) 
        
        return RUMBLE_A;
    
    return RUMBLE_B;
}

function DoGzGetPolar(Current,Received) {
    
    Output = Current / 10 + Received / 10;
    
        if(Output <= -3276) return -32768; 
        if(Output >=  3276) return  32767; 

    return Current + Received; 
} 

function BlockButton(Button) { 

	if (!get_ival(Button))
		return; 
		set_val(Button,Off);
} 
  
function MenuToggle(Main,Vals,Indx,Print,Toggle) { 

	cls_oled(0); 
	MainMenu    = Main; 
	MenuValues  = Vals;
	ModIndex    = Indx;
	Update      = Print;
	MenuSwitch  = Toggle;
	MenuTimeout = Off;
}
  
function PrintMod(ModVal,ModValMin,ModValMax,ModValInc,IndexMin,IndexMax,ModValLbl) { 

	if (Update) { 
 
		rect_oled(2,2,127,46,1,0); 
		Grid  (); 
		printf(6,25,0,1,MiscString[0]);
		NumX = -43; NumY = 10; NumS = -1; 
		FindDigit(ModIndex,DigitValue(ModIndex));
		printf(5,8,0,1,ModValLbl); 

		if (MenuValues) {

			NumX = 0; NumY = 0; NumS = 0;
			FindDigit(ModVal,DigitValue(ModVal));
		} 
			if (MenuSwitch) { 
 
				if (ModVal) {
 
					printf(51,24,1,1,MiscString[1]); 
				}  
    			else { 
					printf(46,24,1,1,MiscString[2]); 
				} 
			} 
		Update = Off; 
	} 

    if (event_press(Up) || get_ival (Up) && get_ptime (Up) >= 450) {
 
        Update = On;
        ModVal += ModValInc;

        if (ModVal >= ModValMax) return ModValMax;

        if (ModVal >= ModValMax) return ModValMax;
    } 
 
    if (event_press(Down) || get_ival (Down) && get_ptime (Down) >= 450) { 

        Update = On;
        ModVal -= ModValInc;

        if (ModVal <= ModValMin) return ModValMin;

        if (ModVal <= ModValMin) return ModValMin;
    }

	if (event_press(Right)) {

		Update = On;
		ModIndex += 1;
 
			if (ModIndex > IndexMax) ModIndex = IndexMin;
	}
  
		if (event_press(Left)) {
			Update = On;
			ModIndex -= 1; 
 
				if (ModIndex < IndexMin) ModIndex = IndexMax;
		} 
	return ModVal;
} 
 
function Grid() { 
  
	line_oled(126,20,2,20,2,1);
	rect_oled(1,1,127,63,0,1); 
	line_oled(126,46,2,46,2,1);
	line_oled(28,20,28,46,2,1);
}
 
function Scroll() {

		ScrollTime += get_rtime();

	if (ScrollTime >= ScrollWait) {
		ScrollWait = ScrollSpeed;
 
		for(ScrollIndex = 1; ScrollIndex <= 17; ScrollIndex++) { 
 
			if(ScrollIndex + ScrollLine >= sizeof(Scroll)) {
				putc_oled(ScrollIndex,Scroll[ScrollIndex + (ScrollLine - sizeof(Scroll))]); 
			} 
				else {  
					putc_oled(ScrollIndex,Scroll[ScrollIndex + ScrollLine]);
				} 
		} 
			puts_oled(ScrollX,ScrollY,0,ScrollIndex,1);
			ScrollLine++; 
 
	if(ScrollLine >= sizeof(Scroll)) {
		ScrollLine = 0;
	} 
		ScrollChar--; 
 
		if(ScrollChar < 1) {
			ScrollChar = 17; 
			ScrollWait = ScrollDelay;
		}
		ScrollTime = 0; 
	} 
}  
    
function FindDigit(Digit,Digits) { 
 
	if (Digit < 0) {  
		putc_oled(Number,45);
		Number += 1;
		Digit = abs(Digit);
		Count = 1;
	} 
	else  
		Count = 0;
    
	if (Digits == 5) {  
		putc_oled(Number,FontDigits[Digit / 10000]);
		Digit = Digit % 10000;
		Number +=  1;
	} 
	if (Digits >= 4) {
		putc_oled(Number,FontDigits[Digit / 1000]);
		Digit = Digit % 1000; 
		Number += 1;
	}  
	if (Digits >= 3) { 
		putc_oled(Number,FontDigits[Digit / 100]); 
		Digit = Digit % 100; 
		Number +=  1; 
	}  
	if (Digits >= 2) { 
		putc_oled(Number,FontDigits[Digit / 10]); 
		Digit = Digit % 10;
		Number += 1; 
	} 
		putc_oled(Number,FontDigits[Digit]); 
		puts_oled(CenterMod(Digits + Count,1) + NumX,25 + NumY,1 + NumS,Number,1);
		Number = 1; 
}   
    
function DigitValue(Number) { 
   
    	Number = abs(Number);
	if (Number / 10000 > 0) return 5;
	if (Number /  1000 > 0) return 4; 
	if (Number /   100 > 0) return 3; 
	if (Number /    10 > 0) return 2; 
		return 1;
} 
   
function CenterMod(Character,Font) { 
    Position = Character * FontSize[Font][0];
    Position = (127 - Position) / 2;
		return Position;
} 
   
/* 
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                   ASCII Table                      ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 
define SPACE       =  32; /*¦¦       ¦¦*/	define  _0 = 48,  A = 65, K = 75, U =  85, e = 101, o = 111, y = 121; 
define EXCLAMATION =  33; /*¦¦   !   ¦¦*/	define  _1 = 49,  B = 66, L = 76, V =  86, f = 102, p = 112, z = 122; 
define QUOTE       =  34; /*¦¦   "   ¦¦*/	define  _2 = 50,  C = 67, M = 77, W =  87, g = 103, q = 113; 
define HASH        =  35; /*¦¦   #   ¦¦*/	define  _3 = 51,  D = 68, N = 78, X =  88, h = 104, r = 114; 
define DOLLAR      =  36; /*¦¦   $   ¦¦*/	define  _4 = 52,  E = 69, O = 79, Y =  89, i = 105, s = 115; 
define PERCENT     =  37; /*¦¦   %   ¦¦*/	define  _5 = 53,  F = 70, P = 80, Z =  90, j = 106, t = 116; 
define AND         =  38; /*¦¦   &   ¦¦*/	define  _6 = 54,  G = 71, Q = 81, a =  97, k = 107, u = 117; 
define APOSTROPHE  =  39; /*¦¦       ¦¦*/	define  _7 = 55,  H = 72, R = 82, b =  98, l = 108, v = 118; 
define O_BRACKET   =  40; /*¦¦   (   ¦¦*/	define  _8 = 56,  I = 73, S = 83, c =  99, m = 109, w = 119; 
define C_BRACKET   =  41; /*¦¦   )   ¦¦*/	define  _9 = 57,  J = 74, T = 84, d = 100, n = 110, x = 120; 
define ASTERISK    =  42; /*¦¦   *   ¦¦*/ 
define PLUS        =  43; /*¦¦   +   ¦¦*/ 
define COMMA       =  44; /*¦¦   ,   ¦¦*/ 
define MINUS       =  45; /*¦¦   -   ¦¦*/ 
define FULLSTOP    =  46; /*¦¦   .   ¦¦*/ 
define F_SLASH     =  47; /*¦¦   /   ¦¦*/ 
define COLON       =  58; /*¦¦   :   ¦¦*/ 
define SEMICOLON   =  59; /*¦¦   ;   ¦¦*/ 
define B_ARROW     =  60; /*¦¦   <   ¦¦*/ 
define EQUAL       =  61; /*¦¦   =   ¦¦*/ 
define F_ARROW     =  62; /*¦¦   >   ¦¦*/ 
define QUESTION    =  63; /*¦¦   ?   ¦¦*/ 
define AT          =  64; /*¦¦   @   ¦¦*/ 
define O_SQUARE    =  91; /*¦¦   [   ¦¦*/ 
define b_SLASH     =  92; /*¦¦   \   ¦¦*/ 
define C_SQUARE    =  93; /*¦¦   ]   ¦¦*/ 
define U_ARROW     =  94; /*¦¦   ^   ¦¦*/ 
define UNDERSCORE  =  95; /*¦¦   _   ¦¦*/ 
define TICK        =  96; /*¦¦   `   ¦¦*/ 
define O_CURLY     = 123; /*¦¦   {   ¦¦*/ 
define BAR         = 124; /*¦¦   |   ¦¦*/ 
define C_CURLY     = 125; /*¦¦   }   ¦¦*/ 
define WAVE        = 126; /*¦¦   ~   ¦¦*/ 
define CROSS       = 127; /*¦¦   PS  ¦¦*/ 
define CIRCLE      = 128; /*¦¦   PS  ¦¦*/ 
define SQUARE      = 129; /*¦¦   PS  ¦¦*/ 
define TRIANGLE    = 130; /*¦¦   PS  ¦¦*/ 
define UP          = 131; /*¦¦ PS+XB ¦¦*/ 
define DOWN        = 132; /*¦¦ PS+XB ¦¦*/ 
define LEFT        = 133; /*¦¦ PS+XB ¦¦*/ 
define RIGHT       = 134; /*¦¦ PS+XB ¦¦*/ 
define VIEW        = 135; /*¦¦   XB  ¦¦*/ 
define MENU        = 136; /*¦¦   XB  ¦¦*/ 

/* 
 .~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~. 
(                   Scroll Array                     ) 
 `-~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~-* 
*/ 
const uint8 Scroll[] = {/* 
 ¦¦> 0 < ¦¦  ¦¦> 1 < ¦¦  ¦¦> 2 < ¦¦  ¦¦> 3 < ¦¦  ¦¦> 4 < ¦¦  ¦¦> 5 < ¦¦  ¦¦> 6 < ¦¦  ¦¦> 7 < ¦¦  ¦¦> 8 < ¦¦  ¦¦> 9 < ¦¦ ¦¦> 10 < ¦¦ ¦¦> 11 < ¦¦ ¦¦> 12 < ¦¦ ¦¦> 13 < ¦¦ ¦¦> 14 < ¦¦ ¦¦> 15 < ¦¦ ¦¦> 16 < ¦¦*/
    SPACE   ,  SPACE   ,  TRIANGLE ,   SPACE   ,     O     ,     r     ,   SPACE   ,     Y     ,   SPACE   ,     T     ,     o     ,   SPACE   ,     E     ,     x     ,     i     ,     t     ,   SPACE   , 
    SPACE   ,  CROSS   ,   SPACE   ,     O     ,     r     ,   SPACE   ,     A     ,   SPACE   ,     T     ,     o     ,   SPACE   ,     N     ,     e     ,     x     ,     t     ,   SPACE   ,    MENU   , 
    SPACE   ,   UP     ,   SPACE   ,     O     ,     r     ,   SPACE   ,   DOWN    ,   SPACE   ,     T     ,     o     ,   SPACE   ,     A     ,     d     ,     j     ,     u     ,     s     ,     t     , 
    SPACE   ,  LEFT    ,   SPACE   ,     O     ,     r     ,   SPACE   ,   RIGHT   ,   SPACE   ,     N     ,     e     ,     x     ,     t     ,   SPACE   ,     M     ,     o     ,     d     ,   SPACE   };
