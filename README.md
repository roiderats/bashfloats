# bashfloats
Bring floating point arithmetics to bash scripts more like integer arithmetics is by {{ bc and curly brackets }}
## Installation
Copy the file name "{{" somewhere to your $PATH. I have it in $HOME/bin/ for now
## Usage
Somewhat similarly like you use ((1 + 2)), use {{ 1.1 + 2.2 }}.
Some differences: 
- You Must have whitespace to separate the starting and ending brackets from the contents
- Output goes to stdout, so to catch it to a variable you need extra $( ) or \`\`
- Quotation .. uh, well, it is like it is. May feel random but obeys rules not scope of this document
### Examples
```
rdr@bash:~$ ((1+2))
rdr@bash:~$ echo $((1+2))
3
rdr@bash:~$ x=$((1+2)) ; echo Answer: x
rdr@bash:~$ {{ 1.0 + 2.5 }}
3.5
rdr@bash:~$ x=$({{ 1.0 + 2.5 }}) ; echo Answer: $x
Answer: 3.5
rdr@bash:~$ {{ 4 \* a\(1\) }}
3.14159265358979323844
rdr@bash:~$ {{ 4*a\(1\) }}
3.14159265358979323844
rdr@bash:~$ {{ scale=5 \; 4 \* a\(1\) }}
3.14156
```

