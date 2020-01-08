---
title: 전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40979061"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


비즈니스용 Skype Online에서 정책을 *전역 범위* 또는 *태그 범위* (또는 *사용자 단위 범위*)에서 구성할 수 있습니다. **Cs** cmdlet을 사용 하는 경우 범위 또는 id를 지정할 필요가 없습니다. 매개 변수 없이 이러한 cmdlet 중 하나를 호출 하면 관련 항목이 모두 반환 됩니다. 예를 들어이 명령은 모든 외부 액세스 정책에 대 한 정보를 반환 합니다.

    Get-CsExternalAccessPolicy

반환 된 데이터를 제한 하려면 Id 매개 변수 또는 Filter 매개 변수만 포함 해야 합니다. 예를 들어 글로벌 정책만 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Identity "global"

Id가 "RedmondAccessPolicy" 인 사용자별 정책을 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 사용자별 정책을 참조 하는 경우 태그 <STRONG>접두사</STRONG> 는 선택 사항입니다. 접두사를 포함 하는이 구문도 사용할 수 있습니다.<BR>Get-CsExternalAccessPolicy – Id "tag: RedmondAccessPolicy"



전역 정책 (즉, 모든 사용자 단위 정책)을 제외한 모든 정책을 반환 하려면 다음 명령을 사용 합니다.

    Get-CsExternalAccessPolicy -Filter "tag:*"

다음 cmdlet은 전역 범위와 사용자 단위 (태그) 범위에 대해 모두 작동 합니다.

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [가져오기-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 이름에 관계 없이 다이얼 플랜은 기능적으로 말하는 정책입니다. 이전 버전의 Lync Server와 함께 사용 되는 용어를 보존 하기 위해 전화 걸기 정책 등의 경우와 같은 방법으로는 <EM>다이얼 플랜</EM> 을 사용 하지 않습니다.



## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

