---
title: 비즈니스용 Skype 서버의 스키마 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 비즈니스용 Skype 서버를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다. 스키마 확장에서는 비즈니스용 Skype 서버에서 요구 하는 클래스 및 특성을 추가 합니다.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815486"
---
# <a name="schema-changes-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 스키마 변경
 
비즈니스용 Skype 서버를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다. 스키마 확장에서는 비즈니스용 Skype 서버에서 요구 하는 클래스 및 특성을 추가 합니다.

> [!NOTE]
> Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 경우 스키마가 변경 되지 않으므로이 문서는 적용 되지 않습니다.
  
비즈니스용 Skype 서버에는 몇 가지 새로운 클래스 및 특성이 필요 하며 일부 기존 클래스 및 특성을 수정 합니다. 또한 비즈니스용 Skype Server에 대 한 많은 구성 정보는 이전 버전 에서처럼 AD DS 대신 중앙 관리 저장소에 저장 됩니다. 다음 정보는 여전히 비즈니스용 Skype 서버의 AD DS에 저장 되어 있습니다.
  
- **스키마 확장**:
    
  - 사용자 개체 확장
    
  - 지원 되는 이전 버전의 Lync Server와의 호환성을 유지 하는 클래스에 대 한 확장입니다.
    
- **데이터** (비즈니스용 Skype Server 확장 스키마 및 기존 스키마 클래스에 저장 됨):
    
  - 사용자 SIP URI (Uniform Resource Identifier) 및 기타 사용자 설정
    
  - 응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체
    
  - 중앙 관리 저장소에 대 한 포인터
    
  - Kerberos 인증 계정 (선택적 컴퓨터 개체)
    
이 항목에서는 비즈니스용 Skype Server에 필요한 Active Directory 스키마 변경 사항에 대해 설명 합니다. 이전 버전의 Office Communications Server에서 도입 된 스키마 변경은 설명 하지 않습니다. 수업 목록과 해당 설명은 [비즈니스용 Skype 서버의 스키마 클래스 및 설명을](schema-classes-and-descriptions.md)참조 하세요. 특성 및 설명 목록은 [비즈니스용 Skype 서버의 스키마 특성 및 설명을](schema-attributes-and-descriptions.md)참조 하세요. 포함 될 수 있는 특성을 가진 클래스 목록은 [비즈니스용 Skype 서버에서 클래스별 스키마 특성](schema-attributes-by-class.md)을 참조 하세요.
  
MsRTCSIP 접두사는 비즈니스용 Skype 서버와 관련 된 클래스 및 특성을 식별 합니다.
  
## <a name="new-active-directory-attributes"></a>새 Active Directory 특성

다음 표에서는 비즈니스용 Skype 서버에 추가 된 Active Directory 특성에 대해 설명 합니다.
  
**비즈니스용 Skype 서버에 의해 추가 된 특성**

|**특성**|**설명**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다. 보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다. 이 특성은 Exchange 2013와 공유 됩니다.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |SIP 라우팅 그룹 ID입니다. 같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.  <br/> |
   
## <a name="modified-active-directory-classes"></a>수정 된 Active Directory 클래스

다음 표에서는 비즈니스용 Skype 서버에서 수정 된 Active Directory 클래스에 대해 설명 합니다.
  
**비즈니스용 Skype 서버에서 수정한 클래스**

|**클래스만**|**바뀌지**|**클래스 또는 특성**|
|:-----|:-----|:-----|
|사용자  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |추가: mayContain  <br/> 추가: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|메일 받는 사람  <br/> |추가: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |추가: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

