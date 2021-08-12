---
title: 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 배포 및 운영하기 비즈니스용 Skype 서버 확장하여 Active Directory 도메인 서비스를 준비해야 합니다. Schema 확장은 사용자 정의에 필요한 클래스 및 특성을 비즈니스용 Skype 서버.
ms.openlocfilehash: 486d642621869cbb23051d2957614f35aa2c67fcda1c539862b05925787f180d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281667"
---
# <a name="schema-changes-in-skype-for-business-server"></a>비즈니스용 Skype 서버
 
배포 및 운영하기 비즈니스용 Skype 서버 확장하여 Active Directory 도메인 서비스를 준비해야 합니다. Schema 확장은 사용자 정의에 필요한 클래스 및 특성을 비즈니스용 Skype 서버.

> [!NOTE]
> Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드하는 경우, 이 문서의 내용은 변경되지 않습니다.
  
비즈니스용 Skype 서버 새 클래스 및 특성이 필요하며 일부 기존 클래스 및 특성을 수정합니다. 또한 이전 버전과 비즈니스용 Skype 서버 AD DS 대신 중앙 관리 저장소에 많은 구성 정보가 저장됩니다. 다음 정보는 여전히 AD DS에 비즈니스용 Skype 서버.
  
- **스키마 확장**:
    
  - 사용자 개체 확장
    
  - 지원되는 이전 버전의 Lync Server와의 호환성을 유지하기 위한 클래스의 확장입니다.
    
- **확장된** 비즈니스용 Skype 서버 및 기존 schema 클래스에 저장되는 데이터:
    
  - 사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정
    
  - 응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체
    
  - 중앙 관리 저장소에 대한 포인터
    
  - Kerberos 인증 계정(선택적 컴퓨터 개체)
    
이 항목에서는 사용자들이 요구하는 Active Directory 비즈니스용 Skype 서버. 이전 버전의 Office 내용은 설명하지 않습니다. 클래스 및 해당 설명 목록은 에서 [Schema 클래스 및 설명을 비즈니스용 Skype 서버.](schema-classes-and-descriptions.md) 특성 및 해당 설명 목록은 [schema attributes and descriptions in 비즈니스용 Skype 서버.](schema-attributes-and-descriptions.md) 포함할 수 있는 특성이 있는 클래스 목록은 [schema attributes by class in 비즈니스용 Skype 서버.](schema-attributes-by-class.md)
  
msRTCSIP prefix는 특정 클래스 및 특성을 식별하며 비즈니스용 Skype 서버.
  
## <a name="new-active-directory-attributes"></a>새 Active Directory 특성

다음 표에서는 이 문서에서 추가한 Active Directory 특성에 대해 비즈니스용 Skype 서버.
  
**특성 추가된 비즈니스용 Skype 서버**

|**특성**|**설명**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |이 다중값 특성은 사용자에 적용되는 유지 정책의 ID를 보유합니다. 유지 정책은 유지 기간 동안 사용자의 사서함 항목을 보존합니다. 이 특성은 2013에서 Exchange 공유됩니다.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |이는 SIP 라우팅 그룹 ID입니다. 동일한 그룹의 사용자는 동일한 프런트 엔드 서버에 등록됩니다.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |이 특성은 프런트 엔드 풀에서 SQL Server 미러된 백 엔드를 저장하는 데 사용됩니다.  <br/> |
   
## <a name="modified-active-directory-classes"></a>수정된 Active Directory 클래스

다음 표에서는 이 문서에서 수정한 Active Directory 클래스에 대해 비즈니스용 Skype 서버.
  
**사용자에 의해 수정된 비즈니스용 Skype 서버**

|**클래스**|**변경 사항**|**클래스 또는 특성**|
|:-----|:-----|:-----|
|사용자  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|담당자  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |추가: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |추가: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

