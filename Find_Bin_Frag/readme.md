# Find_Bin_Frag

Search for a specified **binary fragment** inside a large binary file.  
The search operates at the **byte level**, with no assumptions about encoding.  
Lines or text formatting are not relevant — this is purely a **byte-by-byte comparison**.

## Features

- Works with **files of any size** (limited only by available RAM).  
- Returns the **starting byte positions** of each occurrence.  
- No encoding or conversion required — works directly on raw bytes.  
- Compatible with **Free Pascal Compiler 3.2.2 (Win32)**.  

## Usage



Find_Bin_Frag <MainFile> <FragmentFile>


where:

- `<MainFile>` — path to the main binary file  
- `<FragmentFile>` — path to the binary fragment file  

Output includes:

- the number of occurrences  
- the list of byte offsets where each occurrence begins  

## Performance

Benchmark example on a typical laptop:



Main file size : 1 GB
Fragment size : 64 KB
Matches found : 42
Execution time : ~2 seconds


*(Times may vary depending on file size and hardware.)*

## Technical Details

- The file is read as a **byte array** (via `BlockRead`) with buffering for performance.  
- Comparison is performed purely on **byte sequences**.  
- The fragment must match **exact bytes** of the main file.  
- Designed to handle very large files efficiently without loading everything into memory at once.  

---

Author of idea and implementation — **Iurii Mykhoparkin**  
Developed in collaboration with **ChatGPT**.
