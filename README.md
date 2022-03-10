# qiime1
#installing qiime1
#These are the steps I took in installing qiime1



conda info --envs                       #I had no qiime1 env


conda create -n qiime1 python=2.7 qiime matplotlib=1.4.3 mock nose -c bioconda

#this returned errors: PackagesNotFoundError: The following packages are not available from current channels:  - matplotlib=1.4.3


conda create -n qiime1 python=2.7       #this worked to create the base env

conda activate qiime1
pip install numpy                       #going to try to pip instal 
pip install qiime                       #this sent a list of errors after "Collecting biom-format<2.2.0,>=2.1.4"
                                           #ERROR: Command errored out with exit status 1: command: /mnt/home/rennickb/anaconda3/envs/qiime1/bin/python2.7                                                                   #/mnt/home/rennickb/anaconda3/envs/qiime1/lib/python2.7/site-packages/pip/               
                                            #_vendor/pep517/_in_process.py get_requires_for_build_wheel /tmp/tmpFIIrEd 
                                            #cwd: /tmp/pip-install-3MXGSm/biom-format
                                            #Complete output (13 lines):
                                            #  /tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369: FutureWarning: 
                                            #Cython directive 'language_level' not set, using 2 for now (Py2). This will change in a later release! 
                                            #File: /tmp/pip-install-3MXGSm/biom-format/biom/_filter.pyx
                                            #tree = Parsing.p_module(s, pxd, full_module_name)
                                            #/tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369: FutureWarning: 
                                            #Cython directive 'language_level' not set, using 2 for now (Py2). This will change in a later release! 
                                            #File: /tmp/pip-install-3MXGSm/biom-format/biom/_subsample.pyx
                                            #tree = Parsing.p_module(s, pxd, full_module_name)
                                            #  /tmp/pip-build-env-q_L3vH/overlay/lib/python2.7/site-packages/Cython/Compiler/Main.py:369: 
                                            #FutureWarning: Cython directive 'language_level' not set, using 2 for now (Py2). 
                                            #This will change in a later release! File: /tmp/pip-install-3MXGSm/biom-format/biom/_transform.pyx
                                            #tree = Parsing.p_module(s, pxd, full_module_name)
                                            #Compiling biom/_filter.pyx because it changed.
                                            #  Compiling biom/_transform.pyx because it changed.
                                            #  Compiling biom/_subsample.pyx because it changed.
                                            #  [1/3] Cythonizing biom/_filter.pyx
                                            #  [2/3] Cythonizing biom/_subsample.pyx
                                            #  [3/3] Cythonizing biom/_transform.pyx
                                            #  Python 2.7 is no longer supported
                                            #  ----------------------------------------
                                            #ERROR: Command errored out with exit status 1: /mnt/home/rennickb/anaconda3/envs/qiime1/bin/python2.7 
                                            #/mnt/home/rennickb/anaconda3/envs/qiime1/lib/python2.7/site-packages/pip/_vendor/pep517/_in_process.py 
                                            #get_requires_for_build_wheel /tmp/tmpFIIrEd Check the logs for full command output.
                                            
conda install qiime -c bioconda       #tried this again and it mostly worked.... 
                                      #QIIME base install test results
                                      #===============================
                                      #F.......F
                                      #======================================================================
                                      #FAIL: test_FastTree_supported_version (__main__.QIIMEDependencyBase)
                                      #FastTree is in path and version is supported
                                      #----------------------------------------------------------------------
                                      #Traceback (most recent call last):
                                      #File "/mnt/home/rennickb/anaconda3/envs/qiime1/bin/print_qiime_config.py", line 343, 
                                      #in test_FastTree_supported_version 
                                      #"which components of QIIME you plan to use.")
                                      #AssertionError: FastTree not found. This may or may not be a problem depending on which components of QIIME you plan to use.
                                      #======================================================================
                                      #FAIL: test_uclust_supported_version (__main__.QIIMEDependencyBase)
                                      #uclust is in path and version is supported
                                      #----------------------------------------------------------------------
                                      #Traceback (most recent call last):
                                      #  File "/mnt/home/rennickb/anaconda3/envs/qiime1/bin/print_qiime_config.py", line 322, 
                                      #in test_uclust_supported_version
                                      #"which components of QIIME you plan to use.")
                                      #AssertionError: uclust not found. This may or may not be a problem depending on which components of QIIME you plan to use.
                                      #----------------------------------------------------------------------
                                      #Ran 9 tests in 0.014s
                                      #FAILED (failures=2)
                                  
                                   
#Not sure if those two (FastTree & uclust) are important... I'm going to try demultiplexing and see what my outputs look like. 




