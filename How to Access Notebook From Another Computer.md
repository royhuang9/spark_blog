# How to Access Jupyter Notebook from another computer

https://stackoverflow.com/questions/10538846/how-to-accept-connections-for-ipython-from-other-computers


## First, generate a config file if you don't have it already:
```
jupyter notebook --generate-config
```
Notice the output of this command as it would tell you where the jupyter_notebook_config.py file was generated. Or if you already have it, it will ask you if you would like to overwrite it with the default config. Edit the following line:
```
## The IP address the notebook server will listen on.
c.NotebookApp.ip = '0.0.0.0' # Any ip
```
## For added security, type in a python/IPython shell:
```
from notebook.auth import passwd; passwd()
```
## You will be asked to input and confirm a password string. Copy the contents of the string, which should be of the form type:salt:hashed-password. Find and edit the lines as follows:
```
## Hashed password to use for web authentication.
#  
#  To generate, type in a python/IPython shell:
#  
#    from notebook.auth import passwd; passwd()
#  
#  The string should be of the form type:salt:hashed-password.
c.NotebookApp.password = 'type:salt:the-hashed-password-you-have-generated'

## Forces users to use a password for the Notebook server. This is useful in a
#  multi user environment, for instance when everybody in the LAN can access each
#  other's machine through ssh.
#  
#  In such a case, server the notebook server on localhost is not secure since
#  any user can connect to the notebook server via ssh.
c.NotebookApp.password_required = True

## Set the Access-Control-Allow-Origin header
#  
#  Use '*' to allow any origin to access your server.
#  
#  Takes precedence over allow_origin_pat.
c.NotebookApp.allow_origin = '*'
```
## (Re)start your jupyter notebook, voila!
