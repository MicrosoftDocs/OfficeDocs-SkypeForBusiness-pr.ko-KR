---
title: 비즈니스용 Skype 2015를 통해 클라이언트 환경 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '요약: 이 항목을 읽고 비즈니스용 Skype 사용자에 대한 클라이언트 환경을 구성하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805958"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>비즈니스용 Skype 2015를 통해 클라이언트 환경 구성
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 2015 사용자에 대한 클라이언트 환경을 구성하는 방법을 배워야 합니다.
  
비즈니스용 Skype 2015는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공합니다. 비즈니스용 Skype는 Lync의 모든 기능 외에도 간소화된 컨트롤 및 친숙한 아이콘이 있는 새로운 기능을 제공합니다. 새 클라이언트 경험에 대한 자세한 내용은 비즈니스용 [Skype 탐색을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=529022)
  
비즈니스용 Skype 서버는 새로운 비즈니스용 Skype 클라이언트 환경과 Lync 클라이언트 환경을 지원합니다. 관리자는 사용자의 기본 클라이언트 환경을 선택할 수 있습니다. 예를 들어 조직의 사용자가 새 비즈니스용 Skype 환경을 완전히 교육할 때까지 Lync 클라이언트 환경을 배포할 수 있습니다. 또는 일부 사용자를 비즈니스용 Skype 서버로 아직 업그레이드하지 않은 경우 모든 사용자가 새 서버로 업그레이드될 때까지 모든 사용자가 동일한 클라이언트 환경을 사용할 수 있도록 할 수 있습니다.
  
> [!IMPORTANT]
> 조직에 비즈니스용 Skype 서버와 Lync Server가 모두 배포된 경우 기본 클라이언트 환경은 서버 버전 및 UI 설정에 따라 다릅니다. 사용자가 처음으로 비즈니스용 Skype를 시작하면 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시됩니다. 몇 분이 지난 후 사용자에게 Lync 모드로 전환할지 묻는 요청이 표시됩니다. 자세한 내용은 이 항목의 **부분에 있는** 첫 번째 시작 클라이언트 동작을 참조하세요.
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전 이상에 대한 옵션이 아닙니다. Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x 
  
## <a name="configure-the-client-experience"></a>클라이언트 환경 구성

EnableSkypeUI 매개 변수와 함께 **Set-CSClientPolicy** cmdlet을 사용하여 조직의 사용자가 볼 수 있는 클라이언트 환경을 지정할 수 있습니다.
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

여기서 XdsIdentity는 글로벌 정책 또는 명명된 사이트 정책을 참조합니다.
  
다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택합니다(사이트 또는 사용자별 정책은 글로벌 정책보다 됨). 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택합니다.
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택합니다.
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

조직 내의 특정 사용자에 대해 클라이언트 환경을 구성하려는 경우 **New-CsClientPolicy** cmdlet을 사용하여 새 사용자 정책을 만든 다음 **Grant-CsClientPolicy** cmdlet을 사용하여 특정 사용자에게 정책을 할당할 수 있습니다.
  
예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택하는 새 클라이언트 정책 SalesClientUI를 만듭니다.
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

다음 명령은 Sales 부서의 모든 구성원에게 정책 SalesClientUI를 할당합니다.
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>첫 번째 시작 클라이언트 동작

기본적으로 사용자가 비즈니스용 Skype 2015를 처음 시작하면 이전에 설명한 바와 같이 EnableSkypeUI 매개 변수의 값을 $False Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시됩니다. 몇 분 후에 사용자에게 Lync 모드로 전환할지 묻는 요청이 표시됩니다.
  
사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스를 표시하려는 경우 클라이언트가 업데이트된 후 처음으로 시작되기 전에 다음 단계를 수행합니다.
  
1. 값이 앞서 설명한 $False 정책에서 해당 값으로  `EnableSkypeUI` 설정되어 있는지 확인
    
2. 사용자 컴퓨터에서 시스템 레지스트리를 업데이트합니다. 사용자가 비즈니스용 Skype 클라이언트를 처음 시작하기 전에 이 작업을 한 번만 해야 합니다. 그룹 정책 개체를 만들어 도메인에 가입된 컴퓨터에서 레지스트리를 업데이트하는 방법에 대한 자세한 내용은 이 항목의 부분에 있는 섹션을 참조하십시오.
    
    **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 키에서 새 **Binary 값을** 생성합니다.
    
    값 **이름은** **EnableSkypeUI와** **값** 데이터를 **00 00 00 00으로 설정해야 합니다.**
    
    키는 다음과 같아야 합니다.
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작하면 Lync 사용자 인터페이스가 표시됩니다.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>시작 화면 자습서의 표시 제어

사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 대부분의 사용자가 요청하는 7개 빠른 팁이 포함된 시작 *화면을 표시하는 것입니다.* 시작 화면의 표시를 해제할 수 있지만 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가하여 사용자가 자습서에 액세스할 수 있도록 허용할 수 있습니다.
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에 새 **DWORD(32비트) 값을 생성합니다.** 값 **이름은** **IsBasicTutorialSeenByUser** 및 **값** 데이터를 **1로** 설정해야 합니다.
  
키는 다음과 같아야 합니다.
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>클라이언트 자습서 끄기

사용자가 자습서에 액세스하지 못하게 하려는 경우 다음 레지스트리 값으로 클라이언트 자습서를 해제할 수 있습니다.
  
**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에 새 **DWORD(32비트) 값을 생성합니다.** 값 **이름은** **TutorialFeatureEnabled가** 되어야  합니다. 값 데이터는 **0으로** 설정해야 합니다.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

값 데이터를 **1로** 설정하여 자습서를 **다시 설정할** 수 있습니다.
  
## <a name="default-client-behaviors"></a>기본 클라이언트 동작

조직에 비즈니스용 Skype 서버와 Lync Server가 모두 배포된 경우 클라이언트 환경은 서버 버전 및 Skype UI 설정에 따라 다릅니다. 다음 표에는 서버 버전 및 UI 설정에 따라 초기 클라이언트 환경이 표시됩니다.
  

|**서버 버전**|**EnableSkypeUI 설정**|**클라이언트 환경**|
|:-----|:-----|:-----|
|비즈니스용 Skype 서버 |기본  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버  |True  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버  |거짓  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)  <br/> |
|Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)  <br/> |기본  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)  <br/> |
|Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)  <br/> |True  <br/> |비즈니스용 Skype  <br/> |
|Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)  <br/> |거짓  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)  <br/> |
|Lync Server 2010 또는 Lync Server 2013(패치가 없는 경우)  <br/> |기본  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다(사용자가 나중에 비즈니스용 Skype로 전환할 수 없습니다).  <br/> |
   
다음 표에는 관리자가 Skype UI 환경의 초기 설정을 변경할 때의 클라이언트 환경이 표시됩니다.
  

|**서버 버전**|**EnableSkypeUI 설정**|**클라이언트 UI = Lync**|**클라이언트 UI = 비즈니스용 Skype**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버 |True  <br/> |사용자에게 비즈니스용 Skype로 전환하도록 요청한 경우  <br/> |비즈니스용 Skype  <br/> |
|비즈니스용 Skype 서버 |거짓  <br/> |Lync 모드  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다.  <br/> |
|Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)  <br/> |True  <br/> |사용자에게 비즈니스용 Skype로 전환하도록 요청한 경우  <br/> |비즈니스용 Skype  <br/> |
|Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)  <br/> |거짓  <br/> |Lync 모드  <br/> |사용자에게 Lync 모드로 전환하도록 요청했습니다.  <br/> |
|Lync Server 2010 또는 Lync Server 2013(패치가 없는 경우)  <br/> |기본  <br/> |Lync 모드(비즈니스용 Skype로 전환할 수 없습니다)  <br/> |Lync 모드(비즈니스용 Skype로 전환할 수 없습니다)  <br/> |
   
비즈니스용 Skype 클라이언트의 구성을 관리하는 데 필요한 패치 버전은
  
- Lync Server 2010 - Lync Server 2010용 2015년 2월 누적 업데이트(4.0.7577.710)입니다. 자세한 내용은 [Lync Server 2010용 업데이트를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - Lync Server 2013용 2014년 12월 누적 업데이트(5.0.8308.857) 자세한 내용은 [Lync Server 2013용 업데이트를 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>도메인에 가입된 컴퓨터에서 레지스트리를 수정하는 그룹 정책 개체 만들기

사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작하면 Lync 클라이언트 환경을 표시하는 레지스트리 업데이트가 한 번만 수행됩니다. GPO(그룹 정책 개체)를 사용하여 레지스트리를 업데이트하는 경우 값 데이터를 업데이트하는 대신 새 값을 만들 개체를 정의해야 합니다. GPO를 적용하면 새 값이 없는 경우 GPO에서 GPO를 만들고 값 데이터를 0으로 설정합니다. 
  
다음 절차에서는 사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작하면 Lync 클라이언트 환경이 표시될 수 있도록 레지스트리를 수정하는 방법을 설명합니다. 이 절차를 사용하여 앞에서 설명한 대로 시작 화면 자습서를 사용하지 않도록 레지스트리를 업데이트할 수도 있습니다.
  
### <a name="to-create-the-gpo"></a>GPO를 만들 경우

1. 그룹 정책 **관리 콘솔을 시작합니다.**
    
    그룹 정책 관리 콘솔을 사용하는 방법에 대한 자세한 내용은 그룹 정책 관리 [콘솔을 참조하십시오.](https://go.microsoft.com/fwlink/?LinkId=532759)
    
2. 그룹 정책 개체 **노드를 마우스** 오른쪽 단추로 클릭하고 메뉴에서 **새로** 고침을 선택합니다.
    
3. 새 **GPO** 대화 상자에서 GPO의 이름(예: MakeLyncDefaultUI)을 입력하고 확인을 **클릭합니다.**
    
4. 방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 **편집을** 선택합니다.
    
5. 그룹 **정책** 관리 편집기에서 사용자 **구성을** 확장하고, 기본 설정을 확장하고,  **Windows** 설정을 확장한 다음 레지스트리 **노드를** 선택합니다.
    
6. 레지스트리 노드를 마우스 오른쪽 단추로 **클릭한** 다음 새 레지스트리 **항목을**  >  **선택합니다.**
    
7. 새 레지스트리 속성 **대화 상자에서** 다음을 업데이트합니다.
    
   |**필드**|**선택하거나 입력할 값**|
   |:-----|:-----|
   |**작업** <br/> |**만들기** <br/> |
   |**Hive** <br/> | HKEY_CURRENT_USER <br/> |
   |**키 경로** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Value name** <br/> |EnableSkypeUI  <br/> |
   |**값 형식** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. **확인을** 클릭하여 변경 내용을 저장한 다음 GPO를 닫습니다.
    
그런 다음 만든 GPO를 OU와 같이 정책을 할당하려는 사용자 그룹에 연결해야 합니다.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>GPO를 사용하여 정책을 할당

1. 그룹 정책 관리 콘솔에서 정책을 할당할 OU를 마우스 오른쪽 단추로 클릭한 다음 기존 **GPO에** 대한 링크를 선택합니다.
    
2. **GPO 선택 대화** 상자에서 만든 GPO를 선택하고 확인을 **선택합니다.**
    
3. 대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력합니다.
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. 명령 프롬프트에 다음 명령을 입력합니다.
    
    **gpresult /r**
    
    아래에 표시된 GPO의 이름을 사용하여 "할당된 그룹 정책 개체"가 표시됩니다.
    
레지스트리를 검사하여 GPO가 사용자 컴퓨터에서 레지스트리를 성공적으로 업데이트한지 확인할 수도 있습니다. 레지스트리 편집기를 열고 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] 키로** 이동합니다. GPO가 레지스트리를 성공적으로 업데이트하면 EnableSkypeUI라는 값이 0으로 표시될 것입니다.
  

