# TINYUTF8

### DESCRIPTION
TINYUTF8 is a library for extremely easy integration of Unicode into an arbitrary C++11 project.
The library consists solely of the class "utf8_string", which acts as a drop-in replacement for std::string.
Its implementation is successfully in the middle between small memory footprint and fast access.
Due to its robust architecture, malformed multibyte sequences¹ will be interpreted as ANSI characters (0-255).

¹) That means, the number of adjacent chars >127 is 1 OR if the following characters are >= 192.

### FEATURES
- Drop-in replacement for std::string
- Very Lightweight ~2k LOC
- Very Fast (Random Access is O( Num. Codepoints > 127 ))
- sizeof(utf8_string) = 24bytes (x86)
- Codepoint Range: 0x0 - 0x7FFFFFFF (6 Bytes)
- Single Header file, Single Source file
- NO Exceptions (Defensive Programming)
- Straightforward C++11 design
- Small String Optimization (SSO)
- Even Understands ANSI Strings (Characters 127-255) (with the above mentioned limitations)
- Prepend the UTF8 BOM (Byte Order Mark) to any string when converting it to an std::string
- Supports raw (Byte-based) access (where Speed is needed)

### WHAT TINYUTF8 DOES NOT
- Conversion between iso encodings and utf8
- Other unicode encodings like UTF16 or UTF32
- Visible character comparison ('ch' vs. 'c'+'h')
- Codepoint normalization
