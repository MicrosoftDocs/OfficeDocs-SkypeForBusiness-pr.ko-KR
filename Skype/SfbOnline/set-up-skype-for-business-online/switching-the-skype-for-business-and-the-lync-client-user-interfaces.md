---
title: 비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Microsoft 365 또는 Office 365에서 PowerShell을 사용 하 여 비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환 하는 방법 알아보기 '
ms.openlocfilehash: 02542d11c7315c8f7e183fb78eebf210ead2df94
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164307"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환

비즈니스용 Skype Online 조직의 경우 Microsoft 365 또는 Office 365의 원격 PowerShell을 사용 하 여 비즈니스용 Skype 사용자가 비즈니스용 skype 클라이언트 또는 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스를 사용 하도록 설정할 수 있습니다. 기본 설정은 사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하는 것입니다. Lync 클라이언트 환경을 사용 하려는 경우이 항목의 뒷부분에 나오는 단계에 따라 첫 번째 시작 클라이언트 동작을 관리 하 여 Lync 사용자 인터페이스를 표시할 수 있습니다.
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다. Lync 2013 클라이언트를 사용 하도록 클라이언트 환경을 구성 하기 전에 클라이언트 버전을 확인 하 여 숫자 16으로 시작 되지 않는지 확인 하세요. 예: x.x.x. 
  
> [!TIP]
> 사용자 인터페이스를 쉽게 전환 하 고 수동 단계를 수행 하지 않으려는 경우 PowerShell 스크립트의 [Microsoft 다운로드 센터](https://go.microsoft.com/fwlink/?LinkId=532431) 를 참조 하 여 더 쉽게 만들 수 있습니다.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>사용자의 비즈니스용 Skype 사용자 인터페이스 전환

비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 64 비트 컴퓨터 에서만 지원 되는이 모듈은 [비즈니스용 Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 다른 정보는 [비즈니스용 Skype Online 관리에 맞게 컴퓨터 구성을](https://go.microsoft.com/fwlink/?LinkId=534539)참조 하세요.
  
> [!IMPORTANT]
> 사용자 인터페이스 전환에 대 한 _전역_ 정책 설정은 사용자 지정 정책이 이미 적용 된 사용자에 게 적용 되지 않습니다. 사용자 인터페이스를 변경할 수 있으려면 사용자 지정 정책이 적용 된 각 사용자에 대해 다음을 실행 해야 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_ 정책은 사용자에 대 한 기존 사용자 지정 정책 설정을 대체 하 게 됩니다.
  
조직의 모든 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 설정 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

정책 권한을 설정 하는 경우 다음이 표시 됩니다.
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
조직의 모든 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 설정 하려면 원격 PowerShell을 열고 다음을 입력 합니다. 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

정책 권한을 설정 하는 경우 다음이 표시 됩니다.
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
조직의 단일 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

정책 권한을 설정 하는 경우 다음이 표시 됩니다.
  
![비즈니스용 Skype Online-UI 사용](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
조직의 단일 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

정책 권한을 설정 하는 경우 다음이 표시 됩니다.
  
![비즈니스용 Skype Online-UI 사용 안 함](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
조직의 여러 사용자가 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

조직의 여러 사용자가 비즈니스용 Skype (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

조직의 사용자 그룹이 비즈니스용 Skype 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

조직의 사용자 그룹이 Skype for Business (Lync) 클라이언트를 사용 하도록 허용 하려면 원격 PowerShell을 열고 다음을 입력 합니다.
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  사용자 이름은 정책이 할당 되어야 하는 사용자 계정의 이름입니다. 사용자의 계정 이름은 다음 형식 중 하나로 입력할 수 있습니다: 사용자의 사용자> 도메인\\사용자 이름에 대 한 UPN (>> 사용자의 SIP 주소) 사용자의 Active Directory 표시 이름>
  
[Windows PowerShell을 사용 하 여 Lync Online 관리](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>비즈니스용 Skype Online 정책 설정

이 표에는 정책이 사용자에 게 처음 적용 될 때의 사용자 환경이 나와 있습니다.
  
|**관리 정책 설정**|**표시 되는 사용자 인터페이스**|
|:-----|:-----|
|정책이 설정 되어 있지 않습니다. |이 사용자는 비즈니스용 Skype 클라이언트 사용자 인터페이스를 계속 사용 합니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|이 사용자는 비즈니스용 Skype 클라이언트 사용자 인터페이스를 계속 사용 합니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다. 나중에 전환할 수 있습니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 고 있습니다. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다. 관리자는 향후 비즈니스용 Skype 클라이언트 사용자 인터페이스로 전환 되는 설정을 변경할 수 있습니다. |
   
이 표에는 정책이 변경 되는 경우의 사용자 환경이 나와 있습니다.
  
|**관리 정책 설정**|**비즈니스용 Skype (Lync) 사용자 인터페이스**|**비즈니스용 Skype 사용자 인터페이스**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|사용자가 비즈니스용 Skype 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.  <br/> |사용자가 계속 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 게 됩니다.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|사용자가 계속 해 서 비즈니스용 Skype (Lync) 인터페이스를 사용 하 게 됩니다.  <br/> |사용자가 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스로 전환 하 라는 메시지가 표시 됩니다.  <br/> |
|정책이 설정 되어 있지 않습니다.  <br/> |정책이 설정 되지 않은 경우 사용자는 비즈니스용 Skype (Lync) 클라이언트 사용자 인터페이스가 표시 되지 않습니다. 항상 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 합니다.  <br/> |사용자가 계속 비즈니스용 Skype 클라이언트 사용자 인터페이스를 사용 하 게 됩니다.  <br/> |
   
이 표에는 사용 가능한 모든 온라인 사용자 지정 정책이 나와 있습니다. EnableSkypeUI 플래그 간에 전환 하는 동안 이전 사용자 지정 정책을 유지 하는 데 관리자의 융통성을 제공 하기 위해 생성 된 새 정책이 있습니다. 위의 cmdlet을 사용 하 여 아래 정책 중 하나를 사용자에 게 부여 하세요.
  
|**정책 이름**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |해제|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |해제|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |해제|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |해제|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |해제|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|해제|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |해제|

   
Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
  
- [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>첫 번째 클라이언트 동작 시작

기본적으로 사용자가 비즈니스용 Skype를 처음 실행할 때, 앞에서 설명한 대로 클라이언트 정책을 Lync 클라이언트 환경 (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`)으로 설정 하 여 lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 skype 사용자 인터페이스가 표시 됩니다. 몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.
  
사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스를 표시 하려는 경우 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.
  
1. 이 항목의 앞에 나오는 단계를 따라 클라이언트 정책이 비즈니스용 Skype 사용자 인터페이스를 사용 하지 않도록 설정 되어 있는지 확인 합니다.
    
2. 사용자의 컴퓨터에서 시스템 레지스트리를 업데이트 합니다. 사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하기 전에이 작업을 수행 하 고이 작업을 한 번만 수행 해야 합니다. 도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리를 업데이트 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 있는 섹션을 참조 하세요.
    
    **[HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]** 키에서 새 **이진** 값을 만듭니다.
    
    **값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.
    
    키의 모양은 다음과 같습니다.
    
    [HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab" = dword: 00000001
    
    "CanShareOneNoteInCollab" = dword: 00000001
    
    "CanAppShareInCollab" = dword: 00000001
    
    "EnableSkypeUI" = hex: 00, 00, 00, 00
    
이제 사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스가 표시 됩니다.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>시작 화면 자습서의 표시 제어

사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *가장 사용자가 질문 하는 7 가지 간단한 팁*을 포함 하는 시작 화면을 표시 하는 것입니다. 시작 화면 표시를 해제할 수 있지만, 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가 하 여 사용자가 자습서에 액세스 하도록 허용 합니다.
  
**[\\HKEY_CURRENT_USER 소프트웨어\\Microsoft\\Office\\15.0\\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다. **값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 는 **1**로 설정 되어야 합니다.
  
키의 모양은 다음과 같습니다.
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>클라이언트 자습서 끄기

사용자가 자습서에 액세스할 수 없게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.
  
**[\\HKEY_CURRENT_USER 소프트웨어\\Microsoft\\Office\\15.0\\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다. **값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 는 **0**으로 설정 되어야 합니다.
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리 수정

사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하는 레지스트리 업데이트는 한 번만 수행 해야 합니다. GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들기 위해 개체를 정의 해야 합니다. GPO가 적용 되 면 새 값이 없는 경우 GPO가 생성 하 고 값 데이터를 0으로 설정 합니다.
  
다음 절차에서는 사용자가 비즈니스용 Skype를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다. 또한 앞에서 설명한 대로이 절차를 사용 하 여 레지스트리를 업데이트 하 여 시작 화면 자습서를 사용 하지 않도록 설정할 수 있습니다.
  
 **GPO를 만들려면**
  
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
|**키 경로** <br/> |소프트웨어\\Microsoft\\Office\\Lync  <br/> |
|**값 이름** <br/> |EnableSkypeUI  <br/> |
|**값 형식** <br/> |REG_BINARY  <br/> |
|**값 데이터** <br/> |00000000  <br/> |
   
**확인** 을 클릭 하 여 변경 내용을 저장 한 다음 GPO를 닫습니다.
    
다음에는 OU와 같이 정책을 할당 하려는 사용자의 그룹에 만든 GPO를 연결 해야 합니다.
  
 **GPO를 사용 하 여 정책 할당**
  
1. 그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.
    
2. **Gpo 선택** 대화 상자에서 사용자가 만든 gpo를 선택한 다음 **확인**을 선택 합니다.
    
3. 대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.
    
    **gpupdate/target: user**
    
    "정책 업데이트 중 ..." 메시지가 나타난다 GPO가 적용 되는 동안 표시 됩니다. 완료 되 면 "사용자 정책 업데이트 완료 됨" 이라는 메시지가 표시 됩니다.
    
4. 명령 프롬프트에서 다음 명령을 입력 합니다.
    
    **gpresult/r**
    
    아래에 표시 한 GPO의 이름과 함께 "할당 된 그룹 정책 개체"가 표시 됩니다.
    
또한, 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다. 레지스트리 편집기를 열고 **[HKEY_CURRENT_USER\\소프트웨어\\Microsoft\\Office\\Lync]** 키로 이동 합니다. GPO가 성공적으로 레지스트리를 업데이트 하면 값이 0 인 EnableSkypeUI 이라는 값이 표시 됩니다.
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
