---
title: 회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2957fbc63a885a1c2e1f053cffbf7439d2b648d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40982340"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


조직이 계약 한 모든 오디오 회의 공급자에 대 한 정보를 반환 하려면 매개 변수 없이 [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet을 호출 하면 됩니다.

    Get-CsAudioConferencingProvider

반환 된 데이터를 단일 공급자 (이 예제에서는 공급자 Contoso 오디오 서비스)로 제한 하려면 Id 매개 변수를 사용 합니다.

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

오디오 회의 공급자 ID를 허용 하는 비즈니스용 Skype Online cmdlet이 하나만 있습니다.

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

