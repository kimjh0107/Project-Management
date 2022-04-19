# Start Python Project 
### 1. Pyenv - python version management 
### 2. Poetry - package manager + virtualenv 
### 3. Project Structure 
### Git init 
### Github Connection 

## Contents 
1. Pyenv - python version 관리 
    
    i. 설치 
    ~~~
    git clone https://github.com/pyenv/pyenv.git ~/.pyenv
    ~~~

    ii. pyenv path 설정: Powerlevel10k로 현재 사용중인 shell - zsh -> source .zshrc 
    ~~~
    echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
    echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
    echo 'eval "$(pyenv init --path)"' >> ~/.zprofile
    ~~~

    iii. 원하는 python version 설치 
    ~~~
    # pyenv install [VERSION]
    pyenv version
    pyenv install version
    pyenv install --list  # 설치 가능한 version 확인 
    pyenv install 3.9.12  # pyenv install 3.10.4 -> fail 
    python --version      # version 확인 
    ~~~

    iv. global python 설정 
    ~~~
    pyenv global [VERSION]
    ~~~
    
    v. poetry virtual environment 내부에 설치 (.venv 폴더로)
    ~~~
    poetry config virtualenvs.in-project true
    poetry config virtualenvs.path "./.venv
    ~~~


2. Poetry - package manager + virtualenv 

    i. poetry install 
    ~~~
    pip install poetry 
    ~~~ 
    ii. 프로젝트 폴더 만들기 
    ~~~
    mkdir [PROJECT NAME] && cd [PROJECT NAME] 
    ~~~
    iii. python local version 설정 
    ~~~
    pyenv local [VERSIONS]
    # pyenv local 3.9.12
    ~~~
    iv. 프로젝트 구성 -> version, description ... 작성   
    ~~~
    poetry init
    ~~~
    v. package 설치 
    ~~~
    poetry add [PACKAGE]
    # poetry add numpy
    # poetry add numpy==1.21  # specify the versions 
    ~~~
    vi. virtual env 실행 
    ~~~
    poetry shell 
    ~~~

    ** poetry shell을 해도 module 못 찾을 경우 : 
    ~~~
    source .venv/bin/activate 
    ~~~


3. Project Structure 
    ~~~
    mkdir -p data/raw data/processed src document explore
    ~~~

    ~~~
        .
    ├── data
    │   ├── processed
    │   └── raw
    ├── document
    ├── explore
    ├── main.py
    ├── poetry.lock
    ├── poetry.toml
    ├── pyproject.toml
    ├── README.md
    └── src
    ~~~

4. Git commit workflow  
    i. git init 
    ~~~
    git init 
    ~~~ 
    ii. git add 
    ~~~
    git add . 
    ~~~
    iii. git commit 
    ~~~
    git commit -m "commit message" 
    ~~~
5. Github 연결 
    i. git remote add origin [https:~]
    ~~~
    git remote add origin https://github.com/kimjh0107/Project-Protocol-.git
    ~~~
    ii. git branch -M main 
    ~~~
    git branch -M main 
    ~~~
    iii. git push
    ~~~
    git push --set-upstream origin main     
    ~~~

    * git status : 새롭게 생선된 파일 확인 
    * git add REAME.md : 변경된 파일 add