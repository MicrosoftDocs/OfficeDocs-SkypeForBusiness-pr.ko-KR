---
title: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet
description: 테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet입니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546804"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a>테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


공용 공급자 설정을 수정할 때는 항상 테 넌 트 id를 제공 해야 합니다. 이는 단일 테 넌 트가 있는 경우에도 마찬가지입니다. 예를 들어 다음 명령은 Windows Live를 사용자가 다음과의 통신을 허용 하는 유일한 공용 공급자로 설정 합니다.

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

다행히 이러한 cmdlet 중 하나를 실행할 때마다 테 넌 트 ID (예: bf19b7db-6960-41e5-a139-2aa373474354)를 입력할 필요가 없습니다. 대신, [CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet을 실행 하 고, 변수에 테 넌 트 id를 저장 한 다음, 다른 cmdlet 중 하나를 호출할 때이 변수를 사용 하 여 테 넌 트 id를 검색할 수 있습니다. 예제:

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

또는 테 넌 트 ID를 검색 한 다음 해당 값을 Set-CsTenantPublicProvider cmdlet으로 파이프 하 여 단일 명령으로이 작업을 수행할 수 있습니다.

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

**CsTenant** cmdlet을 호출 하는 경우에는 테 넌 트 ID를 지정할 필요가 없습니다. 이 명령은 테 넌 트에 대 한 정보를 반환 합니다.

    Get-CsTenant

다음 cmdlet은 테 넌 트 id를 받아들입니다. 그러나이 경우 매개 변수는 선택 사항이 며 cmdlet을 호출할 때 입력할 필요가 없습니다. 대신 현재 연결 되어 있는 비즈니스용 Skype Online 테 넌 트를 기반으로 하는 테 넌 트 id를 Windows PowerShell에서 효율적으로 입력 합니다.

  - [CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

예를 들어 다음 명령을 사용 하 여 **CsTenantFederationConfiguration** cmdlet을 호출할 수 있습니다.

    Get-CsTenantFederationConfiguration

필수는 아니지만 Get-CsTenantFederationConfiguration를 호출할 때 테 넌 트 매개 변수를 포함할 수 있습니다.

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

