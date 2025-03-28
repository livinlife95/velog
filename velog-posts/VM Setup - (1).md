<ol>
<li>자동화 시키고 싶다면 먼저 메뉴얼로 할 수 있다는 것을 증명하고 해라</li>
</ol>
<blockquote>
</blockquote>
<p>Oracle VM Virtualbox: 하이퍼바이저
iso: CentOS &amp; Ubuntu
로그인 툴: Git Bash &amp; Putty</p>
<ol start="2">
<li>네트워크 브리징은 가상 머신(VM)이 호스트 컴퓨터의 물리 네트워크 인터페이스와 직접 연결되어, 실제 네트워크 상의 다른 장비와 같은 수준으로 통신할 수 있도록 하는 기술</li>
</ol>
<blockquote>
</blockquote>
<p>VirtualBox: &quot;Bridged Adapter&quot; 옵션을 선택하면 가상 머신이 호스트의 물리 네트워크와 직접 연결되어, 로컬 네트워크 내에서 고유한 IP 주소를 받아 다른 기기와 통신할 수 있습니다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/436f1a22-1245-487f-bfb0-cfa557b6721b/image.png" /></p>
<ol start="3">
<li>Vagrant</li>
</ol>
<ul>
<li>VM 자동화 툴</li>
<li>수동 --&gt; 휴먼 에러 가능성이 있음</li>
<li>OS 설치 없음 (VM Box 사용)</li>
<li>Vagrantfile 이용해서 vm 세팅 관리</li>
<li>단순한 커맨드 ex. vagrant up / vagrant ssh / vagrant halt...</li>
<li>설치하고 싶은 box 확인
<a href="https://portal.cloud.hashicorp.com/vagrant/discover?query=centos%209">https://portal.cloud.hashicorp.com/vagrant/discover?query=centos%209</a></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/a2aee287-12f1-4788-b617-21398a6a5651/image.png" /></p>
<figcaption style="text-align: center; font-size: 15px; color: #808080; margin-top: 40px;">
  vagrant init 명령어로 Vagrantfile 생성
</figcaption>

<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/60a7e414-6a3f-466c-a32d-29f8e36e7fad/image.png" /></p>
<figcaption style="text-align: center; font-size: 15px; color: #808080; margin-top: 40px;">
  vagrant up 명령어로 가상머신 생성 & 시작
</figcaption>

<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/ebf722ef-0366-409d-b840-e1b1422a3291/image.png" /></p>
<figcaption style="text-align: center; font-size: 15px; color: #808080; margin-top: 40px;">
  vagrant list 명령어를 실행하면 다운된 것이 확인된다
  vagrant status 명령어로 보면 running이 확인된다
</figcaption>

<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/3696cdce-c1ff-4faa-ab29-b6d63f91fa98/image.png" /></p>
<figcaption style="text-align: center; font-size: 15px; color: #808080; margin-top: 40px;">
  Oracle VM 관리자에서도 확인이 가능하다
</figcaption>

<p><img alt="" src="https://velog.velcdn.com/images/livinlife95/post/071a202b-ca8d-4dec-b320-51bc84c7897c/image.png" /></p>
<figcaption style="text-align: center; font-size: 15px; color: #808080; margin-top: 40px;">
  vagrant ssh로 생성한 가상머신 접속 (커맨드라인 변화로 접속이 된 것을 확인할 수 있다)
</figcaption>

<p>vagrant halt로 VM 접속 종료
vagrant reload는 Vagrantfile의 변화를 감지하고 다시 접속
vagrant box list로 설치된 box 확인
vagrant global-status로 모든 vm 상태 확인 (power on/off)</p>