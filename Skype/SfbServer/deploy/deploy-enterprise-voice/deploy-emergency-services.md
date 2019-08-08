---
title: 비즈니스용 Skype 서버에서 응급 서비스 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
description: 비즈니스용 Skype Server Enterprise Voice에서 E9 배포-1-1 필수 구성 요소 및 배포 프로세스 검사 목록을 포함 합니다.
ms.openlocfilehash: a96d425f39b53c970047eb220e0ae9f61b515089
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233512"
---
# <a name="deploy-emergency-services-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 응급 서비스 배포
 
비즈니스용 Skype Server Enterprise Voice에서 E9 배포-1-1 필수 구성 요소 및 배포 프로세스 검사 목록을 포함 합니다.
  
확장 9-1-1 (E9-1-1)은 전화 상대의 전화 번호를 도심 또는 주소와 연결 하는 긴급 알림 기능입니다. 이 정보를 사용 하 여 공용 안전 응답 지 (PSAP)에서 이용해의 호출자에 게 즉시 비상 서비스를 발송할 수 있습니다.
  
E9-1-1을 지원 하려면 비즈니스용 Skype 서버에서 위치를 클라이언트에 올바르게 연결 하 고이 정보를 사용 하 여 가까운 PSAP로 긴급 통화를 라우팅할 수 있어야 합니다.
  
## <a name="deployment-prerequisites-for-e9-1-1"></a>E9에 대 한 배포 전제 조건-1-1

E9를 배포 하기 전에 먼저 중앙 관리 저장소, 프런트 엔드 풀 또는 Standard Edition 서버를 비롯 한 비즈니스용 Skype Server 내부 서버를 배포 해야 합니다. 또한 프런트 엔드 서버를 사용 하 여 하나 이상의 중재 서버 (독립 실행형 또는 collocated)를 배포 해야 합니다. 또한 E9-1 배포의 경우 자격 있는 E9-1-1 서비스 공급자에 대 한 SIP 트렁크가 필요 하거나 PSTN (공개 전환 전화 네트워크) 게이트웨이에서 긴급 한 위치 Id 번호 (ELIN) 게이트웨이를 사용 해야 합니다.
  
## <a name="deployment-process"></a>배포 프로세스

다음 표에서는 E9-1-1 배포 프로세스에 대해 간략하게 설명 합니다.
  
|**단계의**|**방법은**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|음성 용도, 경로 및 트렁크 구성 구성  <br/> |1. 새 PSTN 사용 레코드를 만듭니다. 이것은 위치 정책의 **PSTN 사용** 설정에 사용 되는 이름과 같습니다. <br/> 2. 이전 단계에서 만든 PSTN 사용 레코드에 대 한 음성 경로를 만들거나 할당 한 다음 게이트웨이 특성을 E9-1-1 SIP 트렁크 또는 ELIN gateway에 놓습니다.  <br/> 3. SIP 트렁크 E9-1-1 서비스 공급자의 경우 SIP를 통해 E9-1-1 통화를 처리할 트렁크를 설정 하 여 **set-cstrunkconfiguration-EnablePIDFLOSupport** cmdlet을 사용 하 여 PIDF-낮음 데이터를 전달 합니다. <br/> 4. SIP 트렁크 E9-1-1 서비스 공급자의 경우 필요에 따라 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리 되지 않는 통화에 대 한 로컬 PSTN 경로를 만들거나 지정 합니다. 이 경로는 E9 서비스 공급자에 대 한 연결을 사용할 수 없는 경우에 사용 됩니다. E9 서비스 공급자에서 지원 되는 경우 911 다이얼 문자열을 국가/지역 긴급 통화 응답 센터의 직접 안쪽 전화 걸기 () 번호로 변환 하는 트렁크 구성 규칙을 게이트웨이에 할당 합니다.  <br/> |CSVoiceAdmin  <br/> |[비즈니스용 Skype 서버의 E9-1-1 음성 경로 구성](configure-an-e9-1-1-voice-route.md) <br/> |
|위치 정책 만들기 및 사용자 및 서브넷에 할당  <br/> |1. 전역 위치 정책을 검토 합니다.  <br/> 2. 사용자 수준 범위를 사용 하 여 위치 정책을 만듭니다. 또는 조직에 응급 용도가 서로 다른 사이트가 여러 개 있는 경우 네트워크 수준 범위를 사용 하 여 위치 정책을 만듭니다.  <br/> 3. 위치 정책을 네트워크 사이트에 할당 합니다.  <br/> 4. 네트워크 사이트에 적절 한 서브넷을 추가 합니다.  <br/> 5. (선택 사항) 사용자 정책에 위치 정책을 할당 합니다.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin (위치 정책 만들기 제외)  <br/> |[비즈니스용 Skype 서버에서 위치 정책 만들기](create-location-policies.md) <br/> [비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가](add-a-location-policy-to-a-network-site.md) <br/> [네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets) <br/> |
|위치 데이터베이스 구성  <br/> |1. 네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다.  <br/> 2. ELIN 게이트웨이의 경우 \<CompanyName\> 열에 elin를 추가 합니다.  <br/> 3. 주소 확인을 위해 E9-1-1 서비스 공급자에 대 한 연결을 구성 합니다.  <br/> 4. E9-1-1 서비스 공급자를 사용 하 여 주소를 확인 합니다.  <br/> 5. 업데이트 된 데이터베이스를 게시 합니다.  <br/> 6. ELIN 게이트웨이의 경우 PSTN 캐리어의 자동 위치 확인 (ALI) 데이터베이스에 Elin을 업로드 합니다.  <br/> |CSVoiceAdmin  <br/> CSLocationAdmin  <br/> |[비즈니스용 Skype 서버에서 위치 데이터베이스 구성](configure-the-location-database.md) <br/> |
|고급 기능 구성 (선택 사항)  <br/> |1. SNMP 응용 프로그램의 URL을 구성 합니다.  <br/> 2. 보조 위치 정보 서비스의 위치에 대 한 URL을 구성 합니다.  <br/> |CSVoiceAdmin  <br/> |[비즈니스용 Skype 서버에서 SNMP 응용 프로그램 구성](configure-an-snmp-application.md) <br/> [비즈니스용 Skype 서버에서 보조 위치 정보 서비스 구성](secondary-location-information-service.md) <br/> |
   

