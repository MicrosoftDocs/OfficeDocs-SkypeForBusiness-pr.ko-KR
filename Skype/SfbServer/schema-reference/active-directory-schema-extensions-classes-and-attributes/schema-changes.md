---
title: 비즈니스용 Skype 서버의 Schema 변경 사항
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
description: 비즈니스용 Skype 서버를 배포 및 운영하기 전에 해당 스마마를 확장하여 Active Directory 도메인 서비스를 준비해야 합니다. 이 확장은 비즈니스용 Skype 서버에 필요한 클래스 및 특성을 추가합니다.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813578"
---
# <a name="schema-changes-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 Schema 변경 사항
 
비즈니스용 Skype 서버를 배포 및 운영하기 전에 해당 스마마를 확장하여 Active Directory 도메인 서비스를 준비해야 합니다. 이 확장은 비즈니스용 Skype 서버에 필요한 클래스 및 특성을 추가합니다.

> [!NOTE]
> Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드하는 경우 이러한 변경 내용이 적용되지 않습니다.
  
비즈니스용 Skype 서버에는 몇 가지 새로운 클래스 및 특성이 필요하며 일부 기존 클래스 및 특성을 수정합니다. 또한 비즈니스용 Skype 서버에 대한 많은 구성 정보는 이전 버전과 같은 AD DS 대신 중앙 관리 저장소에 저장됩니다. 다음 정보는 여전히 비즈니스용 Skype 서버의 AD DS에 저장됩니다.
  
- **스키마 확장**:
    
  - 사용자 개체 확장
    
  - 지원되는 이전 버전 Lync Server와의 호환성을 유지하기 위한 클래스의 확장입니다.
    
- **데이터(비즈니스용** Skype 서버 확장된 스마마 및 기존 schema 클래스에 저장됨):
    
  - 사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정
    
  - 응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체
    
  - 중앙 관리 저장소에 대한 포인터
    
  - Kerberos 인증 계정(선택적 컴퓨터 개체)
    
이 항목에서는 비즈니스용 Skype 서버에서 요구하는 Active Directory의 변경 내용에 대해 설명합니다. 이전 버전의 Office Communications Server에서 도입된 계획 변경 내용은 설명하지 않습니다. 클래스 및 해당 설명 목록은 비즈니스용 Skype 서버의 Schema 클래스 및 [설명을 참조하세요.](schema-classes-and-descriptions.md) 특성 및 해당 설명 목록은 비즈니스용 Skype 서버의 Schema 특성 및 [설명을 참조하세요.](schema-attributes-and-descriptions.md) 포함할 수 있는 특성이 있는 클래스 목록은 비즈니스용 Skype 서버의 클래스에 따라 [Schema 특성을 참조하세요.](schema-attributes-by-class.md)
  
msRTCSIP prefix는 비즈니스용 Skype 서버와 관련이 있는 클래스 및 특성을 식별합니다.
  
## <a name="new-active-directory-attributes"></a>새 Active Directory 특성

다음 표에서는 비즈니스용 Skype 서버에서 추가한 Active Directory 특성에 대해 설명합니다.
  
**비즈니스용 Skype 서버에서 추가된 특성**

|**특성**|**설명**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |이 다중값 특성은 사용자에 적용되는 유지 정책의 ID를 보유합니다. 유지 정책은 유지 기간 동안 사용자의 사서함 항목을 보존합니다. 이 특성은 Exchange 2013과 공유됩니다.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |이는 SIP 라우팅 그룹 ID입니다. 동일한 그룹의 사용자는 동일한 프런트 엔드 서버에 등록됩니다.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |이 특성은 프런트 엔드 풀에서 SQL Server 미러된 백 엔드를 저장하는 데 사용됩니다.  <br/> |
   
## <a name="modified-active-directory-classes"></a>수정된 Active Directory 클래스

다음 표에서는 비즈니스용 Skype 서버에서 수정한 Active Directory 클래스에 대해 설명하고 있습니다.
  
**비즈니스용 Skype 서버에서 수정된 클래스**

|**클래스**|**변경 사항**|**클래스 또는 특성**|
|:-----|:-----|:-----|
|사용자  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|담당자  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |추가: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |추가: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

