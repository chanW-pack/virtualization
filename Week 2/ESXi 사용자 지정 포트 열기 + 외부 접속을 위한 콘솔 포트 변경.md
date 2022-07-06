# ESXi 사용자 지정 포트 열기 + 외부 접속을 위한 콘솔 포트 변경하기

ESXi에서 새로운 app의 port를 여는 것은 vSphere에서는 불가능하다.

그러므로, ESXi의 서버에 SSH로 접속해서 작업을 진행해야 한다.

<aside>
💡 원래 7.0 버전으로 진행하였으나, 7.0버전부터는 root 계정, 관리자로도 파일 권한변경이 막혔다고 한다. 6.7 버전으로 재설치하여 진행하였다.

</aside>

## 외부 접속 연결 설정

준비물 

- VMware ESXi 설치가 완료된 서버
- 도메인 (없어도 무관)
- SSH 연결 프로그램
- 공유기

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled.png)

> 메뉴 → 호스트 → 관리 → 서비스 → TSM-SSH → 실행 중으로 변경
> 

## ESXi 사용자 지정 포트 열기

VMware ESXi에서 커스텀 포트를 열러면 방화벽 (firewall)을 열어야 한다.

SSH를 열어놓고 쉘로 접속한다.

편집해야 할 파일은

‘ /etc/vmware/firewall/service.xml ‘ 이다.

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%201.png)

> cd 명령어를 사용하요 방화벽 폴더로 이동 후 ls를 일벽해 파일을 확인한다.
> 

service.xml 파일이 있는지 확인한다.

본인은 이미 백업한 파일을 만들어 폴더에서 확인 가능하다.

백업은 cp servie.xml servie.xml.bak 명령으로 생성하였다.

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%202.png)

> 수정하기 전에 파일 권한을 주어야 한다. chmod 명령을 사용하여 권한을 바꾸어준다.
> 

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%203.png)

> 이후 servie.xml 파일을 vi로 편집창을 연다.
> 

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%204.png)

> 파일의 맨 끝에서 코드를 자신에게 맞게 수정하여 추가한다.
> 

```jsx
<service id='[4자리 고유 숫자]'>
  <id>[구분용 고유 문자열]</id>
  <rule id='[4자리 룰 인덱스]'>
    <direction>[방화벽 규칙 inbound, outbound]</direction>
    <protocol>[프로토콜 tcp, udp]</protocol>
    <porttype>[포트 타입 dst]</porttype>
    <port>[허용할 포트]</port>
  </rule>
  <enabled>[사용할지 여부]</enabled>
  <required>[필수]</required>
</service>

<!-- 샘플 -->
<service id='0045'>
  <id>rd2</id>
  <rule id='0001'>
    <direction>inbound</direction>
    <protocol>tcp</protocol>
    <porttype>dst</porttype>
    <port>37161</port>
  </rule>
  <enabled>true</enabled>
  <required>true</required>
</service>
```

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%205.png)

> 다시 권한을 되돌려놓고, 방화벽을 재시작한 뒤 추가한 규칙의 적용을 확인한다.
> 

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%206.png)

> 맨 하단 추가한 규칙이 보인다. 하지만 컴퓨터를 재부팅하게 되면 규칙이 날아간다.
> 

### 트리거 등록

재부팅 시 처음설정값으로 돌아가는 현상을 방지하기 위해

/etc/rc.local.d/local.sh 파일에 추가를 한다.

파일을 열어 마지막 부분의 exit 0 위에 추가 한다.

```jsx
vi /etc/rc.local.d/local.sh 한 뒤

#Job Arranger START
cp /etc/vmware/firewall/service.xml /etc/vmware/firewall/service.xml.bak
chmod 644 /etc/vmware/firewall/service.xml
chmod +t /etc/vmware/firewall/service.xml
sed -i -e 's/<\/ConfigRoot>//g' /etc/vmware/firewall/service.xml
cat<<_EOT_>>/etc/vmware/firewall/service.xml
  <!-- Job Arranger -->
     <service id='1234'>
        <id>CWESXi</id>
        <rule id='5678'>
           <direction>inbound</direction>
           <protocol>tcp</protocol>
           <porttype>dst</porttype>
           <port>9973</port>
        </rule>
        <enabled>true</enabled>
        <required>true</required>
     </service>
< /ConfigRoot>
_EOT_
chmod 444 /etc/vmware/firewall/service.xml
esxcli network firewall refresh
##Job Arranger END

이렇게 해당 내용이 재부팅 시 진행된다는듯 하다.
```

예시로 매일 동일한 시간에 예약작업이 수행되도록 crontabs 에 넣어주는 기능이다.

```jsx
/bin/echo "30 17 * * * /vmfs/volumes/VM_Storage/script/shutdown_esxi.sh" >> /var/spool/cron/crontabs/root

esxcli system maintenanceMode set --enable no
```

ESXi 상태는 UTC를 사용하기 때문에 우리가 원하는 KST 시간을 맞추러면 -9를 해서

계산해 주어야 한다. 02:30에 진행하기 위해선 그보다 9시간 전인 17:30으로 지정해야한다.

---

## ESXi 웹 콘솔 외부에서 접근하기

공유기 아래에 여러 대의 ESXi를 운영할 경우 외부에서 각 ESXi로 접속하기 위해서는 포트를 달리 설정해야 한다.

나는 테스트용으로 2개의 ESXi을 설치하여 외부에서 접근 테스트를 진행하겠다.

우선 공유기와 직접적으로 연결되야 하기 때문에 네트워크 설정을 Bridge로 적용하고 비어있는 주소로 Static IP (고정 아이피) 로 할당했다.

 

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%207.png)

> ESXi 서버 2개를 각각 공유기 bridge 설정으로 고정 할당하였다.
> 

ESXi 1 : 172.16.0.137

ESXi 2 : 172.16.0.138

공유기 외부 IP : **119.194.170.???**

![Untitled](ESXi%20%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1%20%E1%84%8C%E1%85%B5%E1%84%8C%E1%85%A5%E1%86%BC%20%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%A7%E1%86%AF%E1%84%80%E1%85%B5%20+%20%E1%84%8B%E1%85%AC%E1%84%87%E1%85%AE%20%E1%84%8C%E1%85%A5%E1%86%B8%E1%84%89%E1%85%A9%E1%86%A8%E1%84%8B%E1%85%B3%E1%86%AF%20%E1%84%8B%E1%85%B1%E1%84%92%2047bff679f7cd4b9e879d2d1cb646a80d/Untitled%208.png)

이후 공유기에서 443 포트를 알아서 분기해주면 된다.

172.16.0.137 : 9999 포트를 외부에서 사용하고 내부에서 433 포트 사용

172.16.0.138 : 2222 외부포트 443 내부포트

즉, 외부에서 접근시

- 172.16.0.137 은 [https://공인아이피:9999](https://공인아이피:9999)
- 172.16.0.138 은 https://공인아이피:2222

복잡하게 할 필요 없이 잘 적용된다.

참고한 글들중에서는 443포트 자체를 바꾸는 방법도 있는데

[http://isulnara.com/wp/archives/2445](http://isulnara.com/wp/archives/2445)

참고하면 되겠다.

<aside>
💡 공유기와 직접 닿아있는. 즉 Bridge 설정이면 모두 포워딩 가능하다. 예로 개인 PC의 VM 리눅스 서버도 Bridge로 공유기 내부 아이피를 할당 받고 이를 외부포트 1234 내부포트 22 로 연결하면 [https://외부아이피주소:123](https://외부아이피주소:123) 로 접속이 가능해진다.

</aside>