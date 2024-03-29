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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'PowerShell을 사용하여 비즈니스용 Skype 및 Lync 클라이언트 사용자 인터페이스 간에 전환하는 방법을 Microsoft 365 Office 365 '
ms.openlocfilehash: ecb494ea274a9652024056c1b0725159565d22af
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014992"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>비즈니스용 Skype와 Lync 클라이언트 사용자 인터페이스 간 전환

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 온라인 조직의 경우 원격 PowerShell을 사용하여 Microsoft 365 Office 365 사용자가 비즈니스용 Skype 클라이언트 또는 비즈니스용 Skype(Lync) 클라이언트 비즈니스용 Skype 사용할 수 있습니다. 기본 설정은 사용자가 클라이언트 사용자 인터페이스를 비즈니스용 Skype 설정입니다. Lync 클라이언트 환경을 사용 하도록 원하는 경우 이 항목의 나중에 단계를 수행하여 첫 번째 시작 클라이언트 동작을 관리하여 Lync 사용자 인터페이스를 표시할 수 있습니다.
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 2016 클라이언트 비즈니스용 Skype 옵션이 아닙니다. Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않도록 합니다. 예: 16.x.x.x. 
  
> [!TIP]
> 사용자 인터페이스를 쉽게 전환하고 수동 단계를 수행하지 않는 경우 쉽게 만들 수 있도록 PowerShell용 [Microsoft](https://go.microsoft.com/fwlink/?LinkId=532431) 다운로드 센터 스크립트를 참조하세요.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>사용자 비즈니스용 Skype 사용자 인터페이스 전환

Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 다운로드 시 Microsoft 다운로드 센터에서 다운로드하여 [PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)모듈을 Teams 수 있습니다. 기타 내용은 온라인 관리 에 대한 [컴퓨터 비즈니스용 Skype 참조하세요.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
> [!IMPORTANT]
> 사용자  _인터페이스를_ 전환하기 위한 전역 정책 설정은 사용자 지정 정책이 이미 적용된 사용자에게 적용되지 않습니다. 사용자 인터페이스를 변경할 수 있도록 사용자 지정 정책이 적용된 각 사용자에 대해 다음을 실행해야 합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> _ClientPolicyEnableSkypeUI_ 정책은 사용자에 대한 기존 사용자 지정 정책 설정을 대체합니다.
  
조직의 모든 사용자가 클라이언트를 사용하도록 설정하려면 비즈니스용 Skype PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

정책을 오른쪽으로 설정하면 다음이 표시됩니다.
  
![PowerShell: SkypeUIEnabled.](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
조직의 모든 사용자가 Lync(비즈니스용 Skype) 클라이언트를 사용하도록 설정하려면 원격 PowerShell을 열고 다음을 입력합니다. 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

정책을 오른쪽으로 설정하면 다음이 표시됩니다.
  
![PowerShell: SkypeUIDisabled.](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
조직의 단일 사용자가 클라이언트를 사용할 수 있도록 비즈니스용 Skype 원격 PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

정책을 오른쪽으로 설정하면 다음이 표시됩니다.
  
![비즈니스용 Skype 온라인 - UI를 사용하도록 설정합니다.](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
조직의 단일 사용자가 Lync(비즈니스용 Skype) 클라이언트를 사용할 수 있도록 허용하기 위해 원격 PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

정책을 오른쪽으로 설정하면 다음이 표시됩니다.
  
![비즈니스용 Skype 온라인 - UI를 사용하지 않도록 설정했습니다.](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
조직의 여러 사용자가 클라이언트를 사용할 수 있도록 비즈니스용 Skype 원격 PowerShell을 열고 다음을 입력합니다.
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

조직의 여러 사용자가 Lync(비즈니스용 Skype) 클라이언트를 사용할 수 있도록 허용하기 위해 원격 PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

조직의 사용자 그룹이 클라이언트를 사용할 비즈니스용 Skype 원격 PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

조직의 사용자 그룹이 Lync(비즈니스용 Skype) 클라이언트를 사용할 수 있도록 허용하기 위해 원격 PowerShell을 열고 다음을 입력합니다.
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  사용자의 이름은 정책에 할당해야 하는 사용자의 계정의 이름입니다. 사용자의 계정 이름은 사용자의 Active Directory 표시 이름에 대한 사용자 >> 사용자> 사용자> 사용자> SIP 주소 중 하나에 입력할 수 \\ 있습니다.
  
[Lync online을 Windows PowerShell 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="skype-for-business-online-policy-settings"></a>비즈니스용 Skype 온라인 정책 설정

이 표에서는 정책이 사용자에게 처음 적용될 때의 사용자 환경을 보여줍니다.
  
|**관리자 정책 설정**|**표시되는 사용자 인터페이스**|
|:-----|:-----|
|정책이 설정되지 않습니다. |사용자는 클라이언트 사용자 비즈니스용 Skype 계속 사용합니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|사용자는 클라이언트 사용자 비즈니스용 Skype 계속 사용합니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|사용자에게 Lync(Lync) 클라이언트 비즈니스용 Skype 인터페이스로 전환해야 합니다. 나중에 전환할 수 있습니다.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|사용자는 클라이언트 사용자 비즈니스용 Skype 사용합니다. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|사용자에게 Lync(Lync) 클라이언트 비즈니스용 Skype 인터페이스로 전환해야 합니다. 관리자는 향후 클라이언트 사용자 인터페이스로 전환할 설정을 비즈니스용 Skype 수 있습니다. |
   
이 표에서는 정책이 변경될 때의 사용자 환경을 보여줍니다.
  
|**관리자 정책 설정**|**비즈니스용 Skype(Lync) 사용자 인터페이스**|**비즈니스용 Skype 인터페이스**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|사용자는 클라이언트 사용자 인터페이스로 비즈니스용 Skype 표시됩니다.  <br/> |사용자는 클라이언트 사용자 비즈니스용 Skype 계속 사용합니다.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|사용자는 Lync(비즈니스용 Skype) 인터페이스를 계속 사용합니다.  <br/> |사용자에게 Lync(Lync) 클라이언트 비즈니스용 Skype 인터페이스로 전환해야 합니다.  <br/> |
|정책이 설정되지 않습니다.  <br/> |정책이 설정되지 않은 비즈니스용 Skype(Lync) 클라이언트 사용자 인터페이스가 사용자에게는 표시되지 않습니다. 항상 클라이언트 사용자 비즈니스용 Skype 사용합니다.  <br/> |사용자는 클라이언트 사용자 비즈니스용 Skype 계속 사용합니다.  <br/> |
   
이 표에는 사용 가능한 모든 Online 사용자 지정 정책이 표시됩니다. EnableSkypeUI 플래그 간에 전환하는 동안 관리자에게 이전 사용자 지정 정책을 유연하게 유지할 수 있도록 만든 새 정책이 있습니다. 위의 cmdlet을 사용하여 사용자에게 아래 정책 중 하나를 부여하세요.
  
|**정책 이름**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |False|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|False|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |False|

   
다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
  
- [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
## <a name="first-launch-client-behaviors"></a>클라이언트 동작 첫 번째 시작

기본적으로 사용자가 비즈니스용 Skype 처음 시작하면 클라이언트 정책을 Lync 클라이언트 환경()으로 설정하여 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI` 표시됩니다. 몇 분 후에 사용자는 Lync 모드로 전환해야 합니다.
  
사용자가 처음 비즈니스용 Skype 시작할 때 Lync 사용자 인터페이스를 표시하려는 경우 클라이언트가 업데이트된 후 처음으로 시작하기 전에 다음 단계를 따릅니다.
  
1. 이 항목의 앞부분 단계에 따라 클라이언트 정책이 사용자 인터페이스를 사용하지 않도록 설정되어 비즈니스용 Skype 합니다.
    
2. 사용자의 컴퓨터에서 시스템 레지스트리를 업데이트합니다. 사용자가 클라이언트를 처음 시작하기 전에 이 작업을 비즈니스용 Skype 한 번만 실행해야 합니다. 그룹 정책 개체를 만들어 도메인에 가입된 컴퓨터에서 레지스트리를 업데이트하는 방법에 대한 자세한 내용은 항목의 1부 섹션을 참조하세요.
    
    **[HKEY_CURRENT_USER Microsoft Office \\ \\ \\ \\ Lync]** 키에서 새 이진 값을 **생성합니다.**
    
    값 **이름은** **EnableSkypeUI** 되어야  합니다. 값 데이터는 **00 00 00 00으로 설정해야 합니다.**
    
    키는 다음과 같아야 합니다.
    
    [HKEY_CURRENT_USER \\ 소프트웨어 \\ Microsoft \\ Office \\ Lync]
    
    "CanSharePptInCollab"=dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00
    
이제 사용자가 처음 비즈니스용 Skype Lync 사용자 인터페이스가 표시됩니다.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>시작 화면 자습서의 표시 제어

사용자가 클라이언트를 비즈니스용 Skype 경우 기본 동작은 대부분의 사용자가 에 요청하는 빠른 팁 7개가 포함된 시작 *화면을 표시하는 것입니다.* 시작 화면의 표시를 해제할 수 있지만 사용자가 클라이언트 컴퓨터에 다음 레지스트리 값을 추가하여 자습서에 액세스할 수 있도록 허용할 수 있습니다.
  
**[HKEY_CURRENT_USER Microsoft Office \\ \\ \\ \\ \\ Lync]** 키에서 새 **DWORD(32비트) 값을 생성합니다.** 값 **이름은** **IsBasicTutorialSeenByUser** 되어야  합니다. 값 데이터는 **1로 설정해야 합니다.**
  
키는 다음과 같아야 합니다.
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>클라이언트 자습서 해제

사용자가 자습서에 액세스하지 못하게 하려는 경우 다음 레지스트리 값으로 클라이언트 자습서를 해제할 수 있습니다.
  
**[HKEY_CURRENT_USER Microsoft Office \\ \\ \\ \\ \\ Lync]** 키에서 새 **DWORD(32비트) 값을 생성합니다.** 값 **이름은** **TutorialFeatureEnabled 되어야 합니다.** 값 데이터는 **0으로 설정해야 합니다.** 
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

값 데이터를 **1로** 설정하여 자습서를 **다시 설정할** 수 있습니다.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>그룹 정책 개체를 만들어 가입된 도메인 컴퓨터에서 레지스트리를 수정합니다.

사용자가 Lync 클라이언트를 처음 시작하면 Lync 클라이언트 환경을 표시하는 레지스트리 비즈니스용 Skype 한 번만 수행해야 합니다. GPO(그룹 정책 개체)를 사용하여 레지스트리를 업데이트하는 경우 값 데이터를 업데이트하는 대신 새 값을 만들 개체를 정의해야 합니다. GPO가 적용될 때 새 값이 없는 경우 GPO에서 이 값을 만들고 값 데이터를 0으로 설정합니다.
  
다음 절차에서는 사용자가 처음 Lync 클라이언트 환경을 표시할 수 있도록 레지스트리를 수정하는 방법을 비즈니스용 Skype. 이 절차를 사용하여 앞에서 설명한 대로 레지스트리를 업데이트하여 시작 화면 자습서를 사용하지 않도록 설정할 수도 있습니다.
  
 **GPO를 만들면**
  
1. 그룹 **정책 관리 콘솔을 시작합니다.**
    
    그룹 정책 관리 콘솔을 사용하는 방법에 대한 자세한 내용은 그룹 정책 관리 콘솔 [을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))
    
2. 그룹 정책 개체 노드를 마우스 오른쪽 **단추로 클릭하고** 메뉴에서 **새로** 고침을 선택합니다.
    
3. 새 **GPO** 대화 상자에서 GPO(예: MakeLyncDefaultUI)의 이름을 입력한 다음 확인 을 **클릭합니다.**
    
4. 방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 **편집을** 선택합니다.
    
5. 그룹 정책 관리 **편집기에서** 사용자  **구성을** **확장하고** 기본 설정을 확장하고, Windows 설정 확장한 다음 레지스트리 노드를 **선택합니다.**
    
6. 레지스트리 노드를 마우스 오른쪽 **단추로 클릭한** 다음 새 레지스트리 항목   >  **을 선택합니다.**
    
7. 새 **레지스트리 속성 대화** 상자에서 다음을 업데이트합니다.
    
|**필드**|**선택하거나 입력할 값**|
|:-----|:-----|
|**작업** <br/> |**만들기** <br/> |
|**하이브** <br/> | HKEY_CURRENT_USER <br/> |
|**키 경로** <br/> |소프트웨어 \\ Microsoft \\ Office \\ Lync  <br/> |
|**값 이름** <br/> |EnableSkypeUI  <br/> |
|**값 형식** <br/> |REG_BINARY  <br/> |
|**값 데이터** <br/> |00000000  <br/> |
   
**확인을** 클릭하여 변경 내용을 저장한 다음 GPO를 닫습니다.
    
다음으로, 만든 GPO를 OU와 같이 정책을 할당하려는 사용자 그룹에 연결해야 합니다.
  
 **GPO를 사용하여 정책을 할당하는 경우**
  
1. 그룹 정책 관리 콘솔에서 정책을 할당하려는 OU를 마우스 오른쪽 단추로 클릭한 다음 기존 **GPO에** 대한 링크를 선택합니다.
    
2. **GPO 선택 대화** 상자에서 만든 GPO를 선택한 다음 확인 을 **선택합니다.**
    
3. 대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력합니다.
    
    **gpupdate /target:user**
    
    "정책 업데이트..." 메시지 GPO가 적용되는 동안 표시됩니다. 완료되면 "사용자 정책 업데이트가 성공적으로 완료되었습니다"라는 메시지가 표시됩니다.
    
4. 명령 프롬프트에서 다음 명령을 입력합니다.
    
    **gpresult /r**
    
    아래에 만든 GPO의 이름이 표시된 "할당된 그룹 정책 개체"가 표시됩니다.
    
또한 GPO가 레지스트리를 검사하여 사용자의 컴퓨터에서 레지스트리를 성공적으로 업데이트한지 확인할 수 있습니다. 레지스트리 편집기를 열고 **[HKEY_CURRENT_USER Microsoft Office \\ \\ \\ \\ Lync] 키로** 이동합니다. GPO가 레지스트리를 성공적으로 업데이트하면 0의 값으로 EnableSkypeUI라는 값이 표시됩니다.
  
## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
