 # These are the steps I took in installing qiime1
 These include steps that didn't work, but still may be important if residue files lead to making it work.
 
These are the steps I took when installing Anaconda3:<br/>

`bash Anaconda3-2021.11-Linux-x86_64.sh`<br/>
`conda config --set auto_activate_base false`<br/>
`source ~/.bashrc`<br/>
`conda --version`<br/>
`conda create --name py3 python=3`<br/>
`conda activate py3`<br/>
`conda install -n py3 biopython`<br/>
`conda info --envs`<br/>
`conda install constax -c bioconda`<br/>
`conda update constax`<br/>
`conda -V`<br/>


And these are the steps I took to install a working qiime1:

`conda -V` I am running conda 4.11.0 <br/>
`conda info --envs` I had no qiime1 env<br/>


`conda create -n qiime1 python=2.7 qiime matplotlib=1.4.3 mock nose -c bioconda`<br/>
 this returned errors: PackagesNotFoundError: The following packages are not available from current channels: - matplotlib=1.4.3<br/>


`conda create -n qiime1 python=2.7` this worked to create the base env<br/>

`conda activate qiime1`

`pip install numpy` going to try to pip instal <br/>

`pip install qiime` this sent a list of errors after "Collecting biom-format<2.2.0,>=2.1.4"<br/>

	 ERROR: Command errored out with exit status 1: command: /mnt/home/rennickb/anaconda3/envs/qiime1/bin/python2.7   
			/mnt/home/rennickb/anaconda3/envs/qiime1/lib/python2.7/site-packages/pip/   
			 _vendor/pep517/_in_process.py get_requires_for_build_wheel /tmp/tmpFIIrEd  
			 cwd: /tmp/pip-install-3MXGSm/biom-format 
			 Complete output (13 lines): 
			 /tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369: FutureWarning:  
			 Cython directive 'language_level' not set, using 2 for now (Py2). This will change in a later release!  
			 File: /tmp/pip-install-3MXGSm/biom-format/biom/_filter.pyx 
			 tree = Parsing.p_module(s, pxd, full_module_name) 
			 /tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369: FutureWarning:  
			 Cython directive 'language_level' not set, using 2 for now (Py2). This will change in a later release!  
			 File: /tmp/pip-install-3MXGSm/biom-format/biom/_subsample.pyx 
			 tree = Parsing.p_module(s, pxd, full_module_name) 
			 /tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369:  
			 FutureWarning: Cython directive 'language_level' not set, using 2 for now (Py2).  
			 This will change in a later release! File: /tmp/pip-install-3MXGSm/biom-format/biom/_transform.pyx 
			 tree = Parsing.p_module(s, pxd, full_module_name) 
			 Compiling biom/_filter.pyx because it changed. 
			 Compiling biom/_transform.pyx because it changed. 
			 Compiling biom/_subsample.pyx because it changed. 
			 [1/3] Cythonizing biom/_filter.pyx 
			 [2/3] Cythonizing biom/_subsample.pyx 
			 [3/3] Cythonizing biom/_transform.pyx 
			 Python 2.7 is no longer supported 
				---------------------------------------- 
			ERROR: Command errored out with exit status 1: /mnt/home/rennickb/anaconda3/envs/qiime1/bin/python2.7  
			 /mnt/home/rennickb/anaconda3/envs/qiime1/lib/python2.7/site-packages/pip/_vendor/pep517/_in_process.py  
			 get_requires_for_build_wheel /tmp/tmpFIIrEd Check the logs for full command output. 
	 
`conda install qiime -c bioconda` tried this and it mostly worked.... <br/>

	 QIIME base install test results 
			 =============================== 
			 F.......F 
			 ====================================================================== 
			 FAIL: test_FastTree_supported_version (__main__.QIIMEDependencyBase) 
			 FastTree is in path and version is supported 
			 ---------------------------------------------------------------------- 
			 Traceback (most recent call last): 
			 File "/mnt/home/rennickb/anaconda3/envs/qiime1/bin/print_qiime_config.py", line 343,  
			 in test_FastTree_supported_version  
			 "which components of QIIME you plan to use.") 
			 AssertionError: FastTree not found. This may or may not be a problem depending on which components of QIIME you plan to use. 
			 ====================================================================== 
			 FAIL: test_uclust_supported_version (__main__.QIIMEDependencyBase) 
			 uclust is in path and version is supported 
			 ---------------------------------------------------------------------- 
			 Traceback (most recent call last): 
			 File "/mnt/home/rennickb/anaconda3/envs/qiime1/bin/print_qiime_config.py", line 322,  
			 in test_uclust_supported_version 
			 "which components of QIIME you plan to use.") 
			 AssertionError: uclust not found. This may or may not be a problem depending on which components of QIIME you plan to use. 
			 ---------------------------------------------------------------------- 
			 Ran 9 tests in 0.014s 
			 FAILED (failures=2) 
------------------------------------------------------------------------------------------------------------------------------------<br/>
 I dont think I need FastTree & uclust... <br/>
 I'm going to try demultiplexing and see what my outputs look like. <br/>
------------------------------------------------------------------------------------------------------------------------------------<br/>
 Demultiplexing worked great. qiime1 is working.<br/>
 
 Here is what my demultiplexing looks like after it ran: 
 
	 [rennickb@dev-intel14 20210402_Amplicon_PE300]$ `cd demultiplexed_R1_test/`
	 [rennickb@dev-intel14 demultiplexed_R1_test]$ `ll`
	 total 22944769
	 -rw-r----- 1 rennickb plp847_fs2018 131 Mar 10 10:55 histograms.txt
	 -rw-r----- 1 rennickb plp847_fs2018 14870228211 Mar 10 10:55 seqs.fastq
	 -rw-r----- 1 rennickb plp847_fs2018 8625115667 Mar 10 10:55 seqs.fna
	 -rw-r----- 1 rennickb plp847_fs2018 4444 Mar 10 10:55 split_library_log.txt

 




