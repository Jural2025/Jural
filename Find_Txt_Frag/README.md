                               Find_Txt_Frag

Search for a specified text fragment inside a large text file.
The search operates at the byte level, without relying on any encoding
(UTF-8, ANSI, KOI8-R, etc.).
Lines are detected only by CR/LF (0x0D 0x0A) or LF (0x0A).


Features

Works with files of any size (only limited by available RAM).
Line-accurate search — returns exact starting line numbers of occurrences.
No re-encoding required — operates directly on raw bytes.
Compatible with Free Pascal Compiler 3.2.2 (Win32).


Usage

Find_Txt_Frag <MainFile> <FragmentFile>

where:
  <MainFile> — path to the main text file;
  <FragmentFile> — path to the text fragment file.


Output includes:

the number of occurrences;
the list of line numbers where each occurrence begins.


Performance

Benchmark on a 2012 laptop:

Main file       : 800,000 lines
Fragment        :       9 lines
Matches found   :   1,248
Execution time  :      ~1 second


Technical Details

The file is read as a byte array (via BlockRead).
Line breaks are detected by CR/LF.
Comparison is performed purely on byte sequences.
The fragment must match entire lines.
Supports any text encoding based on ASCII (no Unicode conversion).
The encodings of the main file and the fragment file must match.

Author of idea and implementation - Iurii Mykhoparkin.
Developed in collaboration with ChatGPT.
