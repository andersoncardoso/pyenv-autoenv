## install:

1-) first install pyenv:

    git clone git://github.com/yyuu/pyenv.git ~/.pyenv

2-) then just: 

    git clone git@github.com:andersoncardoso/pyenv-autoenv.git ~/.pyenv/plugins/pyenv-autoenv
    
3-) add these lines to your .bashrc or .zshrc:

    if [[ -d $HOME/.pyenv ]];then
        export PATH="$HOME/.pyenv/bin:$PATH"
        eval "$(pyenv init -)"
        source ~/.pyenv/plugins/pyenv-autoenv/bin/pyenv-autoenv
    fi
    
## How it works:

Pyenv already has a behavior where: whenever you enter a directory with a `.python-version` file set 
with a version number in, he autoloads that python version. 

I've extended this behavior to work with virtualenvwrapper. So whenever you enter a dir with a `.python-env` 
set with a virtualenv name, he activates that environment automatically. 

Another aditional behavior is: If you don't have the python version from `.python-version` installed, 
he automatically installs it for you. And if you dont have the virtualenv from `.python-env` created, 
he creates and load it for you.
TODO: make this optional

Example: if you have a project on git with a `.python-version` with `2.7.5` in it, and a  `.python-env` with `my_env`. 
When you clone it, all need to do is `cd` into the project's directory and it will load (and install if needed) both 
the python-2.7.5 and the my_env virtualenv (*uses virtualenvwrapper* so you need to have it installed).

