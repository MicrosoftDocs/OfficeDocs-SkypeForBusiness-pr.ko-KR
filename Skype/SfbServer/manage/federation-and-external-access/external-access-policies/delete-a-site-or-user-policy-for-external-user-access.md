---
title: 외부 사용자 액세스를 위한 사이트 또는 사용자 정책 삭제
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: 외부 액세스 정책 페이지의 비즈니스용 Skype 서버 제어판에 나열된 사이트 또는 사용자 정책을 삭제할 수 있습니다.
ms.openlocfilehash: 2c8d3e73d0bccc0ea7ea25bdfed0b871a51e9a82
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388176"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>외부 사용자 액세스를 위한 사이트 또는 사용자 정책 삭제

더 이상 사용하지 못하도록 외부 사용자 액세스 정책을 만들거나 구성한 경우 다음 방법을 사용할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제합니다.

  - 글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.


외부 액세스 정책 페이지의 비즈니스용 Skype 서버 제어판에 나열된 사이트 또는 사용자 정책을 삭제할 **수** 있습니다. 글로벌 정책을 삭제해도 실제로는 삭제되지는 않지만 외부 사용자 액세스 옵션에 대한 지원은 포함하지 않는 기본 설정으로만 다시 설정됩니다. 글로벌 정책을 다시 설정하는 데 대한 자세한 내용은 외부 사용자 액세스에 대한 글로벌 [정책 다시 설정을 참조합니다](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>외부 사용자 액세스에 대한 사이트 또는 사용자 정책을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다. 

3.  외부 **사용자 액세스를 클릭하고** 외부 **액세스 정책을 클릭합니다**.

4.  외부 **액세스 정책 탭** 에서 삭제할 사이트 또는 사용자 정책을 클릭하고 **편집을 클릭** 한 다음 삭제를 **클릭합니다**.

5.  삭제를 확인하는 메시지가 표시되면 **확인** 을 클릭합니다.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 PIN Windows PowerShell 제거

외부 액세스 정책은 Windows PowerShell cmdlet을 사용하여 삭제할 Remove-CsExternalAccessPolicy 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>특정 외부 액세스 정책을 제거하려면

  - 이 명령은 Redmond 사이트에 적용된 외부 액세스 정책을 제거합니다.<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>사용자 범위에 적용된 모든 외부 액세스 정책을 제거하려면

  - 이 명령은 사용자 범위에서 구성된 모든 외부 액세스 정책을 제거합니다.<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>외부 사용자 액세스를 사용할 수 없는 모든 외부 액세스 정책을 제거하려면

  - 이 명령은 외부 사용자 액세스를 사용하지 않도록 설정한 모든 외부 액세스 정책을 삭제합니다.<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_를 사용합니다. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


자세한 내용은 [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.
