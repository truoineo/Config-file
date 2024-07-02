# Cache Analysis Tool

## Description
This is a tool to identify the hardware characteristics of the cache memory system of a computer. Using microbenchmarking, it has the capability to detect the following parameters:

-Cache Line Size
-Cache Maximum Size
-Cache L3 Size
-Cache Associativity

## Limitation

Please be cautious when using the program as the accuracy of each benchmark vary on a case to case basis. Due to the timing mechanism used, the **Cache Associativity** test is currently limited to x86 architecture only.

## Usage

The program is expected to run on any operating system. To use the tool, please do the following steps:

1. Create the virtual environment: *python3 -m venv myenv*
2. Activate the virtual environment: *source myenv/bin/activate*
3. Install the required dependencies: *pip3 install -r requirements.txt*
4. Run the provided *Makefile* to compile the C/C++ programs: *make all*
5. Run the python script, this would store the outputs in csv files, generate the graphs and give out predictions: *python3 cache_tool.py*

To facilitate modularity, the program is designed in such a way that each of the constituents benchmarks can be run separately using only the C/C++ files. They would output to stdout.

### Structure
The benchmarking C/C++ files of each test and their available options can be found below if the user wants to run them separately:

1. **Cache Line Size**: cache_linesize_benchmark.cpp
2. Cache Maximum Size: cache_maximumsize_benchmark.cpp 
*Option*              | *Description* | *Default value*
----------------------|---------------|----------------
| `--cache_line_size`           | The target computer cache line size | 64               |
3. Cache L3 Size: cache_L3size_benchmark.cpp
*Option*              | *Description* | *Default value*
----------------------|---------------|----------------
| `--maximum_cache_size`           | The size of the highest order cache (Usually correspond to L3 size on normal machine)   | 32 MB               |
4. Cache Associativity 


