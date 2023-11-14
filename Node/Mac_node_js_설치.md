```shell
brew update
brew install nvm
vim ~/.zshenv
```
* brew 로 nvm 설치
* nvm 으로 node 설치 및 버전 관리

```javascript
export NVM_DIR="$HOME/.nvm"
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion
```
* 환경변수 설정

```javascript
source ~/.zshenv
```
* 환경변수 설정 초기화

```javascript
nvm -v
```
* nvm 버전확인

```javascript
nvm ls-remote
```
* 모든 노드 버전 출력

# Reference
1. https://memostack.tistory.com/274

