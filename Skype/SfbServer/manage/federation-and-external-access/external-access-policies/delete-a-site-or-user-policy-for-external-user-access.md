---
title: 외부 사용자 액세스에 대 한 사이트 또는 사용자 정책 삭제
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: 외부 액세스 정책 페이지의 비즈니스용 Skype 서버 제어판에 나열 된 모든 사이트 또는 사용자 정책을 삭제할 수 있습니다.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041237"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>외부 사용자 액세스에 대 한 사이트 또는 사용자 정책 삭제

만들거나 구성한 외부 사용자 액세스 정책을 더 이상 사용하지 않으려면 다음을 수행할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제합니다.

  - 글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.


**외부 액세스 정책** 페이지의 비즈니스용 Skype 서버 제어판에 나열 된 모든 사이트 또는 사용자 정책을 삭제할 수 있습니다. 글로벌 정책을 삭제 해도 실제로 삭제 되지는 않지만이를 기본 설정으로 다시 설정 하면 외부 사용자 액세스 옵션에 대 한 지원이 포함 되지 않습니다. 전역 정책을 다시 설정 하는 방법에 대 한 자세한 내용은 [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md)을 참조 하십시오.


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>외부 사용자 액세스에 대 한 사이트 또는 사용자 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 탭에서 삭제할 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

5.  삭제를 확인하는 메시지가 표시되면 **확인**을 클릭합니다.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거

Windows PowerShell 및 Get-csexternalaccesspolicy cmdlet을 사용 하 여 외부 액세스 정책을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 


## <a name="to-remove-a-specific-external-access-policy"></a>특정 외부 액세스 정책을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 외부 액세스 정책을 제거 합니다.
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>사용자별 범위에 적용 된 모든 외부 액세스 정책을 제거 하려면

  - 이 명령은 사용자별 범위에서 구성 된 모든 외부 액세스 정책을 제거 합니다.
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>외부 사용자 액세스를 사용 하지 않도록 설정 된 모든 외부 액세스 정책을 제거 하려면

  - 이 명령은 외부 사용자 액세스가 해제 된 모든 외부 액세스 정책을 삭제 합니다.
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.
