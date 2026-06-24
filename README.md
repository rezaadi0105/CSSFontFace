# WebKit CSSFontFace Exploit for PS4/PS5

### Vulnerability Scope

|               | CSSFontFace |
| :------------ | :---------- |
| PlayStation 4 | 6.00-13.52  |
| PlayStation 5 | 1.00-13.40  |

### Exploitable In

|               | CSSFontFace |
| :------------ | :---------- |
| PlayStation 4 | 7.00-11.50  |
| PlayStation 5 | 1.00-8.60   |

* PS5 is also exploitable if ASLR can be defeated, either through a heap-shaping trick or a separate leak bug, and the expected vtable pointer can be recovered before the native crash path.

## Supported by This Repository

|               | CSSFontFace |
| :------------ | :---------- |
| PlayStation 4 | 9.00        |
| PlayStation 5 | N/A         |

## Limitations

* Newer WebKit versions on PlayStation 4 [11.5x-latest] and PlayStation 5 [9.00-latest] redesigned CSSFontFace get/set property handling and introduced `m_propertiesOrCSSConnection`. Because of this and other layout changes, the `m_featureSettings` read/write primitive used by this repository is no longer usable on firmware versions above the ranges listed here.
* On PlayStation 5, vtable checks and WebKit ASLR prevent this repository's chain from working unless a separate ASLR defeat and vtable recovery workaround is found.

Technical writeup: https://linearfox.com/blog/cssfontface-uaf-playstation
