---
title: 익명의 사용자 액세스를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 익명 사용자 액세스를 사용하도록 설정하고 사용하지 않도록 설정하는 비즈니스용 Skype 서버.
ms.openlocfilehash: 382bc8bcbfce478677264a6a6da2e791a05b945e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395330"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>사용자 계정에서 익명 사용자 액세스를 비즈니스용 Skype 서버

익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원되는 페더니트 도메인에 사용자 계정이 없는 사용자이지만, 원격으로 조직의 회의에 참가하도록 초대할 수 있는 사용자입니다. 모임에 익명 참가를 허용하면 익명 사용자(즉, 모임 또는 회의 키를 통해서만 ID가 확인된 사용자)가 모임에 참가할 수 있습니다. 익명 참가를 허용하려면 조직에서 익명 참가를 사용하도록 설정해야 합니다.

나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 차단하려는 경우 조직에서 사용하지 않도록 설정할 수 있습니다. 이 섹션의 절차에 따라 조직에 대한 익명 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

> [!NOTE]  
> 조직에 대해 익명 사용자 액세스를 사용하도록 설정하면 액세스 에지 서비스를 실행하는 서버가 익명 사용자의 액세스를 지원하도록만 지정할 수 있습니다. 또한 하나 이상의 회의 정책을 구성하고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지는 익명 사용자가 조직의 모임에 참가할 수 없습니다. 익명 사용자를 모임에 초대할 수 있는 사용자는 익명 사용자를 지원하도록 구성된 회의 정책이 할당된 사용자뿐입니다. 익명 사용자 추가를 지원하기 위해 회의 정책을 구성하는 데 대한 자세한 내용은 [Manage conferencing policies를 참조합니다](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>조직에 대해 익명 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **액세스 에지 구성** 을 클릭합니다.

4.  **액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

5.  **액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.
    
      - 조직에서 익명 사용자 액세스를 사용하도록 설정하려면 익명 사용자와의 통신 사용 확인 **란을 선택합니다** .
    
      - 조직에 대한 익명 사용자 액세스를 사용하지 않도록 설정하려면 익명 사용자와의 통신 사용 확인란 **의 선택을** 취소합니다.

6.  **커밋** 을 클릭합니다.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 익명 사용자 액세스를 Windows PowerShell 사용 안 하도록 설정

**Set-CsAccessEdgeConfiguration** cmdlet과 set-Windows PowerShell 사용하여 익명 사용자 액세스를 관리할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>익명 사용자 액세스를 사용하도록 설정하려면

  - 익명 사용자 액세스를 사용하도록 설정하려면 **AllowAnonymousUsers** 속성 값을 True($True.<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>익명 사용자 액세스를 사용하지 않도록 설정

  - 익명 사용자 액세스를 사용하지 않도록 설정하기 위해 **AllowAnonymousUsers** 속성의 값을 False($False).<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>참고 항목

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
