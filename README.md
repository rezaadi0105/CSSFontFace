# Webkit-CSSFontFace

## Vulnerability Scope

|               | CSSFontFace |  
| :------------ | :-------- |
| PlayStation 4 | 6.00-13.52| 
| PlayStation 5 | 1.00-13.40|

## Exploitable in

|               | CSSFontFace |
| :------------ | :-------- |
| PlayStation 4 | 7.00-11.50| 
| PlayStation 5 | 1.00-8.60| 
* PS5 potentially exploitable with a way to defeat ASLR (either by heap shaping trick or leak bug) and provide expected vtable to survive crash 

## Supported by this Repository

|               | CSSFontFace |
| :------------ | :-------- |
| PlayStation 4 | 9.00| 
| PlayStation 5 | N/A|

* Newer versions of webkit on PlayStation 4 [11.5x-latest] and 5 [9.00-latest] redesigned how CSSFontFace get/set properties and introduced m_propertiesOrCSSConnection, due to that and other factors it causes loss of read/write stopping it from being usable on firmwares higher than stated above.
* On PlayStation 5 vtable checks and ASLR stop it from being usable at all unless a workaround is found.
