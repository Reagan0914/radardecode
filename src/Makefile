#
#       all scripts and executables will be placed in GLOBDIR defined in ../Makefile
#       compilation and link flags are defined here
#
SHELL=/bin/csh
CFLAGS=-O3 -I. -I../include -I/opt/local/include
LFLAGS=-L/opt/local/lib


all: radardecode rotate selectpnts scaletosigma makefits mapsmerge radarfft avgdata stripVme unpriV zerofill fftfilter power_ao convdatatype

clean:
	rm *.o

#comppncode: comppncode.c to_lowercase.o comppnc_init.o comppnc_shiftit.o
#	$(CC) $(CFLAGS) comppncode.c to_lowercase.o comppnc_init.o comppnc_shiftit.o -lm -o $(GLOBDIR)/comppncode

radardecode: radardecode.c unpack_pdev_2c4b_f4.o unpack_pdev_4c4b_rcp_f4.o unpack_pdev_4c4b_lcp_f4.o unpack_pfs_4c4b_lcp_f4.o unpack_pfs_4c4b_rcp_f4.o unpack_pfs_4c2b_lcp_f4.o unpack_pfs_4c2b_rcp_f4.o unpack_pfs_2c4b_f4.o unpack_pfs_2c2b_f4.o unpack_pfs_2c8b_f4.o  to_lowercase.o unpriV_f4.o unpriV_i4.o read_pipe.o timerstart.o timervalue.o compbarkercode.o comppnc_init.o comppnc_shiftit.o comppncode.o
	$(CC) $(CFLAGS) radardecode.c unpack_pdev_2c4b_f4.o unpack_pdev_4c4b_rcp_f4.o unpack_pdev_4c4b_lcp_f4.o unpack_pfs_4c4b_lcp_f4.o unpack_pfs_4c4b_rcp_f4.o unpack_pfs_4c2b_lcp_f4.o unpack_pfs_4c2b_rcp_f4.o unpack_pfs_2c4b_f4.o unpack_pfs_2c2b_f4.o unpack_pfs_2c8b_f4.o  to_lowercase.o unpriV_f4.o unpriV_i4.o read_pipe.o timerstart.o timervalue.o compbarkercode.o comppnc_init.o comppnc_shiftit.o comppncode.o $(LFLAGS) -lfftw3f -lm -o $(GLOBDIR)/radardecode

#
rotate: rotate.c read_pipe.o
	$(CC) $(CFLAGS) rotate.c read_pipe.o -lm -o $(GLOBDIR)/rotate


selectpnts: selectpnts.c read_pipe.o
	$(CC) $(CFLAGS) selectpnts.c read_pipe.o -lm -o $(GLOBDIR)/selectpnts

scaletosigma: scaletosigma.c read_pipe.o to_lowercase.o
	$(CC) $(CFLAGS) scaletosigma.c read_pipe.o to_lowercase.o -lm -o $(GLOBDIR)/scaletosigma

makefits: makefits.c read_pipe.o fitsCmpScl.o fitsOutData.o fitsOutHdr.o
	$(CC) $(CFLAGS) makefits.c read_pipe.o fitsCmpScl.o fitsOutData.o fitsOutHdr.o -lm -o $(GLOBDIR)/makefits

mapsmerge: mapsmerge.c
	$(CC) $(CFLAGS) mapsmerge.c -lm -o $(GLOBDIR)/mapsmerge

radarfft: radarfft.c read_pipe.o
	$(CC) $(CFLAGS) radarfft.c read_pipe.o $(LFLAGS) -lfftw3f -lm -o $(GLOBDIR)/radarfft


avgdata: avgdata.c read_pipe.o to_lowercase.o
	$(CC) $(CFLAGS) avgdata.c read_pipe.o to_lowercase.o -lm -o $(GLOBDIR)/avgdata

stripVme: stripVme.c read_pipe.o 
	$(CC) $(CFLAGS) stripVme.c read_pipe.o -o $(GLOBDIR)/stripVme

unpriV: unpriV.c read_pipe.o unpriV_i4.o unpriV_f4.o unpriV_i2.o unpriV_d8.o 
	$(CC) $(CFLAGS) unpriV.c read_pipe.o unpriV_i4.o unpriV_f4.o unpriV_i2.o unpriV_d8.o -o $(GLOBDIR)/unpriV

zerofill: zerofill.c read_pipe.o
	$(CC) $(CFLAGS) zerofill.c read_pipe.o -lm -o $(GLOBDIR)/zerofill

fftfilter: fftfilter.c read_pipe.o
	$(CC) $(CFLAGS) fftfilter.c read_pipe.o $(LFLAGS) -lfftw3f -lm -o $(GLOBDIR)/fftfilter

power_ao: power_ao.c read_pipe.o 
	$(CC) $(CFLAGS) power_ao.c read_pipe.o -lm -o $(GLOBDIR)/power_ao

convdatatype: convdatatype.c read_pipe.o to_lowercase.o
	$(CC) $(CFLAGS) convdatatype.c read_pipe.o to_lowercase.o -lm -o $(GLOBDIR)/convdatatype


comppnc_init.o:	 comppnc_init.c ; $(CC) $(CFLAGS) -c comppnc_init.c
comppnc_shiftit.o:	 comppnc_shiftit.c ; $(CC) $(CFLAGS) -c comppnc_shiftit.c
comppncode.o:	 comppncode.c ; $(CC) $(CFLAGS) -c comppncode.c
unpriV_f4.o:	 unpriV_f4.c ;  $(CC) $(CFLAGS) -c unpriV_f4.c
unpriV_i4.o:	 unpriV_i4.c ;  $(CC) $(CFLAGS) -c unpriV_i4.c
unpriV_i2.o:	 unpriV_i2.c ;  $(CC) $(CFLAGS) -c unpriV_i2.c
unpriV_d8.o:	 unpriV_d8.c ;  $(CC) $(CFLAGS) -c unpriV_d8.c
read_pipe.o:	 read_pipe.c ;	$(CC) $(CFLAGS) -c read_pipe.c
fitsCmpScl.o:	 fitsCmpScl.c ; $(CC) $(CFLAGS) -c fitsCmpScl.c
fitsOutData.o:	 fitsOutData.c ;$(CC) $(CFLAGS) -c fitsOutData.c
fitsOutHdr.o:	 fitsOutHdr.c ; $(CC) $(CFLAGS) -c fitsOutHdr.c
timerstart.o:	 timerstart.c ; $(CC) $(CFLAGS) -c timerstart.c
timervalue.o:	 timervalue.c ; $(CC) $(CFLAGS) -c timervalue.c
to_lowercase.o:	 to_lowercase.c ; $(CC) $(CFLAGS) -c to_lowercase.c
unpack_pdev_4c4b_lcp_f4.o:   unpack_pdev_4c4b_lcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pdev_4c4b_lcp_f4.c
unpack_pdev_4c4b_rcp_f4.o:   unpack_pdev_4c4b_rcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pdev_4c4b_rcp_f4.c
unpack_pdev_2c4b_f4.o:   unpack_pdev_2c4b_f4.c ; $(CC) $(CFLAGS) -c unpack_pdev_2c4b_f4.c
unpack_pfs_4c4b_lcp_f4.o:   unpack_pfs_4c4b_lcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_4c4b_lcp_f4.c
unpack_pfs_4c4b_rcp_f4.o:   unpack_pfs_4c4b_rcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_4c4b_rcp_f4.c
unpack_pfs_4c2b_lcp_f4.o:   unpack_pfs_4c2b_lcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_4c2b_lcp_f4.c
unpack_pfs_4c2b_rcp_f4.o:   unpack_pfs_4c2b_rcp_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_4c2b_rcp_f4.c
unpack_pfs_2c4b_f4.o:   unpack_pfs_2c4b_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_2c4b_f4.c
unpack_pfs_2c2b_f4.o:   unpack_pfs_2c2b_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_2c2b_f4.c
unpack_pfs_2c8b_f4.o:   unpack_pfs_2c8b_f4.c ; $(CC) $(CFLAGS) -c unpack_pfs_2c8b_f4.c
compbarkercode.o:	 compbarkercode.c ; $(CC) $(CFLAGS) -c compbarkercode.c
comppncode.a:     comppncode.c comppnc_init.o comppnc_shiftit.o; $(CC) $(CFLAGS) -c comppncode.c; ar cr comppncode.a comppncode.o comppnc_init.o comppnc_shiftit.o
