# github-actions-demo
Repo for building and testing Github Actions

#Getting started

1. Go to your cloud environmnet
1. Open terminal
1. Create a virtual environment in the cloud environment:
    * Use: ```python3 -m venv ~/.github-actions-demo```
    * The venv will be called `.github-actions-demo`
1. Activate the virtual env with:
    * Activate: ```source ~/.github-actions-demo/bin/activate```


## Notes
* See which Python you're using:
    * `which python`
    * returns `/home/NAME/.github-actions-demo/bin/python`

* Create `requirements.txt`
    * In terminal type to create file `touch requirements.txt`  
    * Enter libraries you want:
    ```
    black
    pylint
    pytest
    pytest-cov
    click
    ```  
* Create a Makefile to automate steps:
    * Terminal: `touch Makefile`
    * Structure of file (The spacing in file is IMPORTANT):
    ```
    install:
	    pip install --upgrade pip &&\
	    pip install -r requirements.txt

    format:
        black *.py

    lint:
        pylint --disable=R,C hello.py

    test:
        python -m pytest -vv --cov=hello test_hello.py
    ```


* Add itentity to terminal to push changes:
    * Interminal type:
    ```
    git config --global user.name "im-octocat"
    git config --global user.email "EMAIL ADDRESS"
    ```
    * When doing `git push` you will be prompted for credentials. Enter:
      * Your github username: `im-octocat`
      * Your generated token (CTRL+SHIFT+V). You wil have to make token and IMPORTANT TO MAKE SURE YOU SET PERMISSIONS:
      	* Create a [token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic) and [permissions to have](https://stackoverflow.com/questions/71953666/remote-permission-to-repository-denied-url-returned-error-403).
