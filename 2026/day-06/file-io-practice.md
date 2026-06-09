# Day 06 - linux Fundamentals: Read and Write Text Files

## 

- Creating a file

    - $ touch notes.txt

- writing text to a file and appending

    - $ echo "adding line 1" > notes.txt
    - $ echo "appending line 2" >> notes.txt
    - $ echo "using tee cmd adding line_3" | tee -a notes.txt

- Reading the file back

    - $ cat notes.txt
    - $ tail -n 2 notes.txt
    - $ head -n 2 notes.txt

