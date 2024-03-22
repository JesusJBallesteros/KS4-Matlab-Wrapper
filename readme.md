Package by Jesus J. Ballesteros. 03.2024
The matlab script is supposed to be implemented in a running pipeline. Probably can be a standalone script.
Accepts few inputs to feed the specific paths and variables of a current pipeline.
It explains how to proceed to set up a workstation ready to KS4.
It prepares the enviroment in every single run and the arguments that need to be passed to the python script.
It requires the CUSTOMIZATION of the 'parameters.py'. We copy a prepared version to the main working directory of the enviroment.

CONTAINS: 

master_kilosort4.m
% Implementation of a MATLAB wrapper to the newly developed Kilosort4, which runs
% completely under python. To be used with the API version, programatically, 
% during a regular session processing.
%
% Fundamental algorithm from MOUSELAND KILOSORT GITHUB. Cite the toolbox and paper:
% https://github.com/MouseLand/Kilosort
% General documentation: https://kilosort.readthedocs.io/en/latest/
%

parameters.py
# CUSTOMIZED file with specific settings for a project
# No fundamental changes, only the DEFAULT values have been changed
# The file is copied from a defined storage folder to the working directory

master_kilosort4.py
# This file, together with a customized 'parameters.py' are copied to the kilosort enviroment 
# folder before the call happens in MATLAB.
#
# MATLAB call lives in 'master_kilosort4.m'. This call is of the shape:
# pyrunfile("master_kilosort4.py \                                          % master script (this file)
#           'C:\code\miniconda3\envs\kilosort\Lib\site-packages\kilosort' \ % enviroment place
#           '...\data\preprocessing\913\20240219' \                         % bin file absolute location
#           '32' \                                                          % number of channels
#           '...\analysisCode\chanMapE32-S2_linearized_DeutSN11.mat' \      % absolute path to probe map
#           "                                                               % end of string
#