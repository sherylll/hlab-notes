Take from /asap/fic/proj_hunga/pr_base/rasbpi (where the sources files can be found)

To run Lenet on 2 boards

Board1: Compute
flat2lenet/rasbpi
sudo ./settble lenet1.dat
sudo ./wb_write

Board0: I/O 
flat2io/rasbpi
sudo ./settbl io0.dat
sudo ./write_image


settbl: Only setting the table

sloop: Test program for AIST send.v for wrap
send.v generates packet by itself.
sudo ./sloop loop.dat test0.dat (test1.dat) fic08 id=0
sudo ./sloop pass.dat test0.dat (test1.dat) fic07 id=1

sloop1: Test program for counting packets: send1.v for wrap (flat2.bin)
sudo ./sloop1 loop.dat test0.dat (test1.dat) fic08 id=0
sudo ./sloop pass.dat test0.dat (test1.dat) fic07 id=1

loopc: Test program for checking packets: lcheck.v for wrap (flat2lback.bin)
counting packet by packet  
sudo ./loopc loop.dat test0.dat (test1.dat) fic08 id=0
sudo ./loopc pass.dat test0.dat (test1.dat) fic07 id=1

loopc1: Test program for checking packets: lcheck.v for wrap (flat2lback.bin)
counting 8-packet by 8-packet  
sudo ./loopc1 loop.dat test0.dat (test1.dat) fic08 id=0
sudo ./loopc1 pass.dat test0.dat (test1.dat) fic07 id=1

sring: Simple ring program with 4boards. (flat2)
sudo ./sring ring.dat test0.dat   fic08 id=0
sudo ./sring 1to2.dat test0.dat   fic07, fic05
sudo ./sring 2to1.dat test0.dat   fic06

ringc: ring transfer check program with 4boards. (flat2lback.bin)
sudo ./ringc ring.dat test0.dat   fic08 id=0
sudo ./ringc 1to2.dat test0.dat   fic07, fic05
sudo ./ringc 2to1.dat test0.dat   fic06