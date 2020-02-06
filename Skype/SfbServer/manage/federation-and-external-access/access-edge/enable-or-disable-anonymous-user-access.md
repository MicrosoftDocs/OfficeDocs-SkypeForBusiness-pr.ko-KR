---
title: 익명 사용자 액세스 사용 또는 사용 안 함
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818409"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 익명 사용자 액세스 사용 또는 사용 안 함

익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참여 하도록 초대 받을 수 있는 사용자입니다. 모임에서 익명 참가를 허용 하면 익명 사용자 (즉, 모임 또는 회의 키를 통해 id를 확인 하는 사용자)가 모임에 참가할 수 있습니다. 익명 참가를 허용 하려면 조직에 대해 사용 하도록 설정 해야 합니다.

나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 방지 하려면 조직에 맞게 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대 한 익명 사용자 액세스를 설정 하거나 해제 합니다.

> [!NOTE]  
> 조직에 대 한 익명 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 익명 사용자의 액세스를 지원 하도록 지정할 수만 있습니다. 익명 사용자는 하나 이상의 회의 정책을 구성 하 고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지 조직의 모임에 참가할 수 없습니다. 익명 사용자를 모임에 초대할 수 있는 유일한 사용자는 익명 사용자를 지원 하도록 구성 된 회의 정책이 할당 된 사용자입니다. 익명 사용자 초대를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 [회의 정책 관리](../../conferencing/conferencing-policies.md)를 참조 하세요.

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>조직에 대 한 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.

4.  **액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.
    
      - 조직에서 익명 사용자 액세스를 사용 하도록 설정 하려면 **익명 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 조직에서 익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **익명 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 익명 사용자 액세스 사용 또는 사용 안 함

Windows PowerShell 및 **Set-CsAccessEdgeConfiguration** cmdlet을 사용 하 여 익명 사용자 액세스를 관리할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

## <a name="to-enable-anonymous-user-access"></a>익명 사용자 액세스를 사용 하도록 설정 하려면

  - 익명 사용자 액세스를 사용 하도록 설정 하려면 **AllowAnonymousUsers** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>익명 사용자 액세스를 사용 하지 않도록 설정 하려면

  - 익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **AllowAnonymousUsers** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>참고 항목

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
