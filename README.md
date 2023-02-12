# feh_CSST1
The code is used to estimate the metallicity of the dwarf stars and giant stars from the CSST filter systems. It is worth noting that only FGK-type stars are valid. \
dwarf_feh is a astronomy Python package specifically designed to estimate  the metallicity of the dwarf stars from CSST filter systems.\
giant_feh is a astronomy Python package specifically designed to estimate the metallicity of the giant stars from CSST filter systems.\
# How to install

    from PyPI (recommmend)
    pip install feh
# Quick start 
 The input are u, g and i magnitudes and color error, then we can derive the metallicity of the dwarf stars from dwarf_feh package. The output are two files named dwarf_feh_predicted.csv and dwarf_feh_error.csv, the former stores the photometric metallicity and the latter stores the random error of photometric metallicity.\

from feh import dwarf_feh\
dwarf_feh.dwarf_feh(u,g,i,error)\

# An example
If a file (dwarf_feh.csv) is given, u, g, i magnitudes are contained in this file.

py\
import pandas as pd\
error=0.01\

data=pd.read_csv('giant_feh.csv')\
u0=data.loc[:,['u']].values\
g0=data.loc[:,['g']].values\
i0=data.loc[:,['i']].values\
u,g,i=u0.flatten(),g0.flatten(),i0.flatten()\
xdata,ydata=g-i,u-g\
dwarf.dwarf_feh(u,g,i,error)\

# API
dwarf_feh(u,g,i,error)

    Args:
        u: array-like, shape (n, )
           CSST u band
        
        g: array-like, shape (n, )
           CSST g band
           
        i: array-like, shape (n, )
           CSST i band
           
        error: float
           color error 

giant_feh(u,g,i,error)

    Args:
        u: array-like, shape (n, )
           CSST u band
        
        g: array-like, shape (n, )
           CSST g band
           
        i: array-like, shape (n, )
           CSST i band
           
        error: float
           color error
