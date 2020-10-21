# Node js 설치
자신의 컴퓨터에 node.js를 설치합니다. 우리는 NVM(Node Version Manager)를 이용해 node.js를 설치합니다. NVM을 사용하면 다양한 node.js version을 쉽게 설치하고 사용할 수 있습니다.

## **macOS 및 Linux(ubuntu)에서 node.js 설치**

### **1. NVM 설치**

아래 명령어를 터미널에 입력합니다.

```
$ touch ~/.bash_profile 
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

---

### **1.1. 주의사항**

우분투의 경우 `Command 'curl' not found` 메세지가 터미널에 출력될 수 있습니다. 이는 `curl`이라는 프로그램이 설치되어 있지 않기 때문입니다.

아래 명령어를 통해 `curl`을 설치한 다음, **다시** 위에 있는 NVM설치 명령어를 입력해 주세요.

```
$ sudo apt-get update
$ sudo apt install curl
```

---

성공적으로 NVM이 설치되었으면 NVM 버전을 확인합니다.

```
$ nvm --version
```

버전이 잘 나온다면 성공적으로 NVM이 설치된 것입니다.

### **2. node.js 설치**

NVM을 설치했으니 이제 NVM을 이용하여 node.js를 설치해 봅시다.
NVM을 이용해 node.js를 설치하는 방법은 간단합니다. 아래 명령어와 같이 설치하고자하는 node version을 적어주시면 됩니다.

```
$ nvm install 12.18.3
```

성공적으로 node가 설치되었으면 node 버전을 확인합니다.

```
$ node -v
```

버전이 잘 나온다면 성공적으로 node가 설치된 것입니다.