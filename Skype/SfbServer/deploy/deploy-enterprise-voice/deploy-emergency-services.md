---
title: 비즈니스용 Skype 서버에서 긴급 서비스 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 비즈니스용 Skype 서버에서 E9-1-1을 Enterprise Voice. 선행 단계 및 배포 프로세스 검사 목록을 포함합니다.
ms.openlocfilehash: 8aed5b6462ecf9d5d9fecfb0ffdc5573ca4f2352
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812528"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 긴급 서비스 배포
 
비즈니스용 Skype 서버에서 E9-1-1을 Enterprise Voice. 선행 단계 및 배포 프로세스 검사 목록을 포함합니다.
  
E9-1-1(Enhanced 9-1-1)은 발신자 전화 번호를 구민 또는 주소와 연결하는 긴급 알림 기능입니다. 이 정보를 사용하여 PSAP(Public Safety Answering Point)는 긴급 상황에 처한 발신자에게 즉시 긴급 서비스를 보낼 수 있습니다.
  
E9-1-1을 지원하려면 비즈니스용 Skype 서버가 위치를 클라이언트와 올바르게 연결하고 이 정보를 사용하여 긴급 통화를 가장 가까운 PSAP로 라우팅할 수 있어야 합니다.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1의 배포 선행 구성

E9-1-1을 배포하기 전에 중앙 관리 저장소, 프런트 엔드 풀 또는 Standard Edition 서버를 비롯한 비즈니스용 Skype 서버 내부 서버를 이미 배포해야 합니다. 또한 독립 실행형 또는 프런트 엔드 서버와 함께 배치된 하나 이상의 중재 서버를 배포해야 합니다. 또한 E9-1-1 배포를 수행하려면 적격 E9-1-1 서비스 공급자에 대한 SIP 트렁크 또는 PSTN(Public Switched Telephone Network)에 대한 ELIN(Emergency Location Identification Number) 게이트웨이가 필요합니다.
  
## <a name="deployment-process"></a>배포 프로세스

다음 표에서는 E9-1-1 배포 프로세스에 대한 개요를 제공합니다.
  
|**작업 단계**|**단계**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|음성 사용, 경로 및 트렁크 구성 구성  <br/> |1. 새 PSTN 사용 레코드를 만들 수 있습니다. 위치 정책의 **PSTN** 사용 설정에 사용되는 이름과 동일합니다. <br/> 2. 이전 단계에서 만든 PSTN 사용 레코드에 음성 경로를 만들거나 할당한 다음 게이트웨이 특성을 E9-1-1 SIP 트렁크 또는 ELIN 게이트웨이를 지정합니다.  <br/> 3. SIP 트렁크 E9-1-1 서비스 공급자의 경우 **Set-CsTrunkConfiguration -EnablePIDFLOSupport** cmdlet을 사용하여 SIP를 통해 E9-1-1 통화를 처리할 트렁크를 설정하여 PIDF-LO 데이터를 전달합니다. <br/> 4. 선택적으로 SIP 트렁크 E9-1-1 서비스 공급자의 경우 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리하지 않는 통화에 대한 로컬 PSTN 경로를 만들거나 할당합니다. E9-1-1 서비스 공급자에 대한 연결을 사용할 수 없는 경우 이 경로가 사용됩니다. E9-1-1 서비스 공급자가 지원하는 경우 911 전화 문자열을 ECRC(국가/지역 응급 통화 응답 센터)의 DID(Direct Inward Dialing) 번호로 변환하는 게이트웨이에 트렁크 구성 규칙을 할당합니다.  <br/> |CSVoiceAdmin  <br/> |[비즈니스용 Skype 서버에서 E9-1-1 음성 경로 구성](configure-an-e9-1-1-voice-route.md) <br/> |
|위치 정책을 만들고 사용자 및 서브넷에 할당  <br/> |1. 전역 위치 정책을 검토합니다.  <br/> 2. 사용자 수준 범위를 사용하여 위치 정책 만들기 또는 조직에 긴급 사용이 다른 사이트가 두 개 이상 있는 경우 네트워크 수준 범위를 사용하여 위치 정책을 만들 수 있습니다.  <br/> 3. 네트워크 사이트에 위치 정책을 할당합니다.  <br/> 4. 네트워크 사이트에 적절한 서브넷을 추가합니다.  <br/> 5. (선택 사항) 위치 정책을 사용자 정책에 할당합니다.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin(위치 정책 만들기 제외)  <br/> |[비즈니스용 Skype 서버에서 위치 정책 만들기](create-location-policies.md) <br/> [비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가](add-a-location-policy-to-a-network-site.md) <br/> [네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|위치 데이터베이스 구성  <br/> |1. 위치에 대한 네트워크 요소 매핑으로 데이터베이스를 채우기  <br/> 2. ELIN 게이트웨이의 경우 열에 ELIN을 \<CompanyName\> 추가합니다.  <br/> 3. 주소 유효성을 검사하기 위해 E9-1-1 서비스 공급자에 대한 연결을 구성합니다.  <br/> 4. E9-1-1 서비스 공급자를 사용하여 주소의 유효성을 검사합니다.  <br/> 5. 업데이트된 데이터베이스를 게시합니다.  <br/> 6. ELIN 게이트웨이의 경우 PSTN 통신 사업자 ALI(자동 위치 식별) 데이터베이스에 ELIN을 업로드합니다.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[비즈니스용 Skype 서버에서 위치 데이터베이스 구성](configure-the-location-database.md) <br/> |
|고급 기능 구성(선택 사항)  <br/> |1. SNMP 응용 프로그램의 URL을 구성합니다.  <br/> 2. 보조 위치 정보 서비스의 위치에 대한 URL을 구성합니다.  <br/> |CSVoiceAdmin  <br/> |[비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성](configure-an-snmp-application.md) <br/> [비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성](secondary-location-information-service.md) <br/> |
   

