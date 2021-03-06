---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Oracle 플러그인 설치

Oracle 플러그인은 추가 기능이며 Oracle 데이터베이스 호스트의 Linux Agent 또는 Windows Agent로 설치됩니다. {{site.data.keyword.backup_notm}} 포털을 통해 작업을 구성하고 안전한 원격 저장소에 Oracle 데이터베이스를 백업하며 Oracle 데이터베이스를 복원할 수 있습니다. Oracle 플러그인은 기존 아키텍처로 통합됩니다.

**제공되는 기능**

- Oracle 데이터베이스 백업 및 복구 지원.
- Oracle 플러그인은 전체 온라인 데이터베이스 인스턴스의 ARCHIVELOG 기반, 비-RMAN 백업을 제공합니다. 모든 비임시 테이블스페이스와 인스턴스 매개변수 파일은 자동으로 백업됩니다. Oracle Corporation에서는 데이터베이스 작업이 뜸한 기간에 백업을 받도록 권장합니다.
- 전체 및 부분 데이터베이스는 보통의 사용자 관리되는 Oracle 복구 메커니즘을 통해 복원됩니다.

**제한사항**
- 로컬, 단일 인스턴스, 디스크 기반 데이터베이스만 백업됩니다.
- 데이터베이스 클러스터는 백업되지 않습니다.
- 원시 디바이스는 백업되지 않습니다.
- 원격 데이터베이스는 백업되지 않습니다.
- 데이터베이스는 ARCHIVELOG 모드에서 실행되어야 하며, 백업이 구성된 사용자에게 SYSDBA 권한이 있어야 합니다.
- 데이터베이스 비밀번호는 스크립트 기반 메소드에서 보안성 강화를 위해 암호화됩니다.

## 플러그인 주문

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){:new_window}에 로그인하여 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오. <br/>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 계정을 선택하고 **플러그인 주문**을 클릭하십시오.
4. **{{site.data.keyword.backup_notm}} 플러그인 - Oracle**을 선택하고 **계속**을 클릭하십시오.
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.
7. 서드파티 서비스 계약을 읽고 동의한다고 표시하려면 상자를 선택하십시오.
8. **주문하기**를 클릭하십시오.

## Windows용 Oracle 플러그인 설치

Windows용 Oracle 플러그인은 32비트 또는 64비트 Windows 에이전트로 설치됩니다. Oracle 플러그인을 설치하려면 에이전트 설치 킷을 실행하십시오. Oracle 플러그인은 **사용자 설치** 페이지에서 옵션으로 나타납니다.

Microsoft Windows 서버용 플러그인을 설치하기 전에 `services.msc`에서 두 {{site.data.keyword.backup_notm}} 서비스를 모두 중지하십시오.
{:tip}

1. `c:\installs\evault` 폴더를 찾아보고 상위 개정 번호로 .exe 파일을 실행하십시오.
2. 언어 화면에서 **확인**을 클릭하십시오.
3. 시작 화면에서 **다음**을 클릭하십시오.
4. **설치 수정**을 선택하고 **다음**을 클릭하십시오.
5. **미변경 상태 유지**를 선택하고 **다음**을 클릭하십시오.
6. 사용자 설치 화면에서 구매한 각 플러그인을 선택하고 **이 기능이 설치될 위치...**를 선택한 후에 **다음**을 클릭하십시오.
7. **내 현재 등록 유지**를 선택하고 **다음**을 클릭하십시오.
8. **설치**를 클릭하십시오.
9. 설치가 완료되면 두 서비스가 모두 사용되고 실행 중인지 확인하십시오.
10. {{site.data.keyword.backup_notm}} 포털에서 데이터베이스 액세스/보기가 가능하면 설치가 완료된 것입니다.

## Linux용 Oracle 플러그인 설치

Oracle 플러그인은 Linux Agent에 대한 추가 기능으로 데이터베이스 호스트의 에이전트로 설치됩니다. Oracle 플러그인을 설치하기 전에 Linux Agent 애플리케이션을 설치해야 합니다. 에이전트는 32비트 애플리케이션 및 64비트 애플리케이션으로 사용 가능합니다. 자세한 정보는 [Linux에 {{site.data.keyword.backup_notm}} 클라이언트 설치](install-backup-client-linux.html)를 참조하십시오. 

Oracle 플러그인 설치 킷은 tar.gz 파일로 사용 가능합니다.

1. 호스트에서 설치 패키지를 다운로드하십시오.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. 패키지에서 파일의 압축을 푸십시오.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. 해당 폴더로 이동하십시오.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. 설치 스크립트를 실행하십시오.
   ```
   # ./install.sh
   ```
   {: pre}

5. 화면의 설치 지시사항을 따르십시오.

Oracle 플러그인은 데이터베이스가 ARCHIVELOG 모드로 실행되도록 요구하는 "불일치" 전체 데이터베이스 백업을 수행합니다. DBA는 백업이 시작되기 전에 데이터베이스가 ARCHIVELOG 모드인지 확인해야 합니다. 자세한 정보는 사용자 안내서를 참조하십시오.
{:important}


## 사용자 안내서 다운로드

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서를 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오.
