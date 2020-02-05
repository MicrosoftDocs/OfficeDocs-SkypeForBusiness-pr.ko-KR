---
title: 비즈니스용 Skype 2015 클라이언트 환경 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '요약: 비즈니스용 Skype 사용자에 대 한 클라이언트 환경을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: 678bda8499ddae61f0cca3b3bbb606283192660b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769081"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>비즈니스용 Skype 2015 클라이언트 환경 구성
 
**요약:** 비즈니스용 Skype 2015 사용자에 대 한 클라이언트 환경을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.
  
비즈니스용 skype 2015는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공 합니다. Lync의 모든 기능 외에도 비즈니스용 Skype는 간단한 컨트롤과 친숙 한 아이콘과 함께 새로운 기능을 제공 합니다. 새로운 클라이언트 환경에 대 한 자세한 내용은 [비즈니스용 Skype 살펴보기](https://go.microsoft.com/fwlink/?LinkId=529022)를 참조 하세요.
  
비즈니스용 skype 서버는 Lync 클라이언트 환경을 비롯 하 여 새로운 비즈니스용 Skype 클라이언트 환경을 지원 합니다. 관리자는 사용자를 위해 기본 클라이언트 환경을 선택할 수 있습니다. 예를 들어 조직의 사용자가 새로운 비즈니스용 Skype 환경에서 완벽 하 게 교육을 받을 때까지 Lync 클라이언트 환경을 배포할 수 있습니다. 또는 모든 사용자를 비즈니스용 Skype 서버에 아직 업그레이드 하지 않은 경우 모든 사용자가 새로운 서버로 업그레이드 될 때까지 동일한 클라이언트 환경을 사용할 수 있습니다.
  
> [!IMPORTANT]
> 조직에서 비즈니스용 Skype 서버와 Lync Server를 배포한 경우 서버 버전과 UI 설정에 따라 기본 클라이언트 환경이 달라 집니다. 사용자가 비즈니스용 Skype를 처음 실행할 때 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다. 몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다. 자세한 내용은이 항목의 뒷부분에 나오는 **첫 번째 클라이언트 동작 시작** 을 참조 하세요.
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전 이상에 대 한 옵션이 아닙니다. Lync 2013 클라이언트를 사용 하도록 클라이언트 환경을 구성 하기 전에 클라이언트 버전을 확인 하 여 숫자 16으로 시작 되지 않는지 확인 하세요. 예: x.x.x. 
  
## <a name="configure-the-client-experience"></a>클라이언트 환경 구성

조직의 사용자가 EnableSkypeUI 매개 변수가 있는 **Set CSClientPolicy** cmdlet을 사용 하 여 볼 클라이언트 환경을 지정할 수 있습니다.
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

여기서 XdsIdentity는 글로벌 정책 또는 명명 된 사이트 정책을 참조 합니다.
  
다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다 (사이트 또는 사용자 특정 정책이 전역 정책 보다 우선 하는 경우 유의 함). 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택 합니다.
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다.
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

조직 내 특정 사용자에 대 한 클라이언트 환경을 구성 하려는 경우 **새 csclientpolicy** cmdlet을 사용 하 여 새 사용자 정책을 만든 다음 **부여-csclientpolicy** cmdlet을 사용 하 여 특정 사용자에 게 정책을 할당할 수 있습니다.
  
예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택 하는 새 클라이언트 정책, SalesClientUI를 만듭니다.
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

다음 명령은 Sales 부서의 모든 구성원에 게 정책, SalesClientUI를 할당 합니다.
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>첫 번째 클라이언트 동작 시작

기본적으로 사용자가 처음으로 비즈니스용 Skype 2015을 실행 하는 경우 EnableSkypeUI 매개 변수 값을 설정 하 여 Lync 클라이언트 환경을 선택한 경우에도 설명 된 대로 $False에는 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다. 앞서. 몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.
  
사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스를 표시 하려는 경우 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.
  
1. 앞에서 설명한 대로 사용 `EnableSkypeUI` 하 고 있는 정책의 값이 $False으로 설정 되어 있는지 확인 합니다.
    
2. 사용자의 컴퓨터에서 시스템 레지스트리를 업데이트 합니다. 사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하기 전에이 작업을 수행 하 고이 작업을 한 번만 수행 해야 합니다. 도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리를 업데이트 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 있는 섹션을 참조 하세요.
    
    **[HKEY_CURRENT_USER \software\microsoft\office\lync]** 키에서 새 **이진** 값을 만듭니다.
    
    **값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.
    
    키의 모양은 다음과 같습니다.
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

이제 사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스가 표시 됩니다.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>시작 화면 자습서의 표시 제어

사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *가장 사용자가 질문 하는 7 가지 간단한 팁*을 포함 하는 시작 화면을 표시 하는 것입니다. 시작 화면 표시를 해제할 수 있지만, 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가 하 여 사용자가 자습서에 액세스 하도록 허용 합니다.
  
**[HKEY_CURRENT_USER \software\microsoft\office\15.0\lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다. **값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 는 **1**로 설정 되어야 합니다.
  
키의 모양은 다음과 같습니다.
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>클라이언트 자습서 끄기

사용자가 자습서에 액세스할 수 없게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.
  
**[HKEY_CURRENT_USER \software\microsoft\office\15.0\lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다. **값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 는 **0**으로 설정 되어야 합니다.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.
  
## <a name="default-client-behaviors"></a>기본 클라이언트 동작

조직에 비즈니스용 Skype 서버와 Lync Server가 배포 되어 있는 경우 클라이언트 환경은 서버 버전과 Skype UI 설정에 따라 달라 집니다. 다음 표에는 서버 버전과 UI 설정을 기반으로 하는 초기 클라이언트 환경이 나와 있습니다.
  

|**서버 버전**|**EnableSkypeUI 설정**|**클라이언트 환경**|
|:-----|:-----|:-----|
|비즈니스용 Skype 서버 |기본값  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버  |False  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버  |해제  <br/> |사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)  <br/> |기본값  <br/> |사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)  <br/> |False  <br/> |비즈니스용 Skype  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)  <br/> |해제  <br/> |사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (패치 없이)  <br/> |기본값  <br/> |사용자가 Lync 모드로 전환 요청 (사용자가 나중에 비즈니스용 Skype로 전환할 수 없음)  <br/> |
   
다음 표에는 관리자가 Skype UI 환경에 대 한 초기 설정을 변경할 때 클라이언트 환경이 표시 됩니다.
  

|**서버 버전**|**EnableSkypeUI 설정**|**클라이언트 UI = Lync**|**클라이언트 UI = 비즈니스용 Skype**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버 |False  <br/> |사용자가 비즈니스용 Skype로 전환 하도록 요청 했습니다.  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버 |해제  <br/> |Lync 모드  <br/> |사용자가 Lync 모드로 전환 요청  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)  <br/> |False  <br/> |사용자가 비즈니스용 Skype로 전환 하도록 요청 했습니다.  <br/> |비즈니스용 Skype  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)  <br/> |해제  <br/> |Lync 모드  <br/> |사용자가 Lync 모드로 전환 요청  <br/> |
|Lync Server 2010 또는 Lync Server 2013 (패치 없이)  <br/> |기본값  <br/> |Lync 모드 (비즈니스용 Skype로 전환할 수 없음)  <br/> |Lync 모드 (비즈니스용 Skype로 전환할 수 없음)  <br/> |
   
비즈니스용 Skype 클라이언트의 구성을 관리 하는 데 필요한 패치 버전은 다음과 같습니다.
  
- Lync Server 2010-Lync Server 2010에 대 한 4.0.7577.710 (2015 년 2 월 누적 업데이트). 자세한 내용은 [Lync Server 2010 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532771) 를 참조 하세요.
    
- Lync Server 2013-Lync Server 2013 용 5.0.8308.857 (2014 누적 업데이트) 자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532772)를 참조 하세요.
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리 수정

사용자가 처음으로 비즈니스용 Skype 2015 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하는 레지스트리 업데이트는 한 번만 수행 해야 합니다. GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들기 위해 개체를 정의 해야 합니다. GPO가 적용 되 면 새 값이 없는 경우 GPO가 생성 하 고 값 데이터를 0으로 설정 합니다. 
  
다음 절차에서는 사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다. 또한 앞에서 설명한 대로이 절차를 사용 하 여 레지스트리를 업데이트 하 여 시작 화면 자습서를 사용 하지 않도록 설정할 수 있습니다.
  
### <a name="to-create-the-gpo"></a>GPO를 만들려면

1. **그룹 정책 관리 콘솔**을 시작 합니다.
    
    그룹 정책 관리 콘솔을 사용 하는 방법에 대 한 자세한 내용은 [그룹 정책 관리 콘솔](https://go.microsoft.com/fwlink/?LinkId=532759)을 참조 하세요.
    
2. **그룹 정책 개체** 노드를 마우스 오른쪽 단추로 클릭 하 고 메뉴에서 **새로 만들기** 를 선택 합니다.
    
3. **새 gpo** 대화 상자에서 GPO 이름 (예: MakeLyncDefaultUI)을 입력 한 다음 **확인**을 클릭 합니다.
    
4. 방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **편집** 을 선택 합니다.
    
5. **그룹 정책 관리 편집기**에서 **사용자 구성**, **기본 설정**, **Windows 설정을**차례로 확장 한 다음 **레지스트리** 노드를 선택 합니다.
    
6. **레지스트리** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새** > **레지스트리 항목**을 선택 합니다.
    
7. **새 레지스트리 속성** 대화 상자에서 다음을 업데이트 합니다.
    
   |**칸**|**선택 하거나 입력할 값**|
   |:-----|:-----|
   |**작업** <br/> |**만드는** <br/> |
   |**벌** <br/> | HKEY_CURRENT_USER <br/> |
   |**키 경로** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**값 이름** <br/> |EnableSkypeUI  <br/> |
   |**값 형식** <br/> |REG_BINARY  <br/> |
   |**값 데이터** <br/> |00000000  <br/> |
   
8. **확인** 을 클릭 하 여 변경 내용을 저장 한 다음 GPO를 닫습니다.
    
다음에는 OU와 같이 정책을 할당 하려는 사용자의 그룹에 만든 GPO를 연결 해야 합니다.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>GPO를 사용 하 여 정책 할당

1. 그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.
    
2. **Gpo 선택** 대화 상자에서 사용자가 만든 gpo를 선택한 다음 **확인**을 선택 합니다.
    
3. 대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. 명령 프롬프트에서 다음 명령을 입력 합니다.
    
    **gpresult/r**
    
    아래에 표시 한 GPO의 이름과 함께 "할당 된 그룹 정책 개체"가 표시 됩니다.
    
또한, 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다. 레지스트리 편집기를 열고 **[HKEY_CURRENT_USER \software\microsoft\office\lync]** 키로 이동 합니다. GPO가 성공적으로 레지스트리를 업데이트 하면 값이 0 인 EnableSkypeUI 이라는 값이 표시 됩니다.
  

