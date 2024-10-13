# SWE_2021_41_2024_2_week_6

## Week 4 Assignment
* [Week 4 Assignment Repository Link](https://github.com/g7199/SWE_2021_41_2024_2_week_4 "Repository Week 4")
* 
  
  ```python
  def isHappy(n):

  seen_table = []
  queue = [n]

  while queue:
    target = queue.pop(0)

    if target in seen_table:
      return False
    seen_table.append(target)

    sum = 0
    while target != 0:
      digit = target%10
      target //= 10

      sum += digit ** 2

    queue.append(sum)

    if sum == 1:
      return True

  return False
  ```
* Code Discription
1. **`seen_table`**  
   - 역할: 이미 한 번 계산한 수를 저장하는 리스트.  
   - 목적: 무한 루프를 방지하기 위함. 만약 계산 과정에서 동일한 수가 두 번 나오면, 이는 순환을 의미하므로 해당 수는 'happy number'가 아님.
   
2. **`queue`**  
   - 역할: 계산할 수를 관리하는 큐.  
   - 목적: 주어진 수 `n`을 기반으로 계산이 진행되며, 각 단계에서 새로운 합계를 큐에 추가하여 반복적으로 계산하도록 함. `queue.pop(0)`을 통해 첫 번째 요소를 제거하면서 계산을 진행함.
   
3. **`sum`**  
   - 역할: 각 자리 숫자의 제곱합을 저장하는 변수.  
   - 목적: 현재 숫자의 각 자리수를 제곱한 후 이를 모두 더하여 새로운 숫자를 생성함. 이 숫자가 1이 되면 해당 숫자는 'happy number'로 판정됨.

4. `queue`를 통해 숫자를 하나씩 꺼내 계산하고, 각 자리 숫자의 제곱합을 `sum`에 저장하며, `seen_table`로 이전에 나온 숫자를 추적하여 순환 여부를 확인해 'happy number'를 판별함.
 
 ## Week 5 Assignment
 ```bash 
 docker exec ossp-container cat /etc/os-release
 ```
 ossp-container 컨테이너에서 /etc/os-release 파일의 내용을 cat을 통해 출력한다. 즉, ossp-container의 운영체제 정보를 출력한다.
 ```
PRETTY_NAME="Ubuntu 24.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.1 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID LIKE=debian
HOME_URL="https://www.ubuntu.com/'
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy'
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
 ```

 ```bash
 docker exec ossp-container git --version
 ```
 ossp-container 컨테이너에 접속해서 설치된 git의 버전을 확인한다.
```
git version 2.43.0
```

 ```bash
 docker exec ossp-container python3 -- version
 ```
 ossp-container 컨테이너에 접속해서 python3의 버전을 확인한다.
```
Python 3.12.3
```

 ```bash
docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
 ```
 ossp-container 컨테이너의 .HostConfig.Binds 속성을 출력한다. 이는 호스트의 파일 경로와 컨테이너의 파일 경로간 바인드 마운트된 정보를 가지고 있어, 호스트와 컨테이너 간 연결된 경로를 출력한다.
```
[/Users/g7199/Desktop/ossp:/mnt/ossp]
```
