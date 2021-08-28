---
title: 2013에서 ELIN 게이트웨이의 위치 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: ELIN 게이트웨이를 사용하여 E9-1-1 배포를 위해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: bb0656909866a793bc8d64635b17785020dd646d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596512"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>2013에서 ELIN 게이트웨이의 위치 비즈니스용 Skype 서버

ELIN 게이트웨이를 사용하여 E9-1-1 배포를 위해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.

네트워크에서 비즈니스용 Skype 서버 위치를 자동으로 제공하려면 다음 작업을 수행해야 합니다.

- 네트워크 와이어맵으로 위치 정보 서비스 데이터베이스를 채우고 CompanyName 필드에 LINS(Emergency Location Identification Numbers)를 포함합니다.

- 네트워크의 클라이언트에서 사용할 수 있도록 위치를 게시합니다.

- 업로드 PSTN(전화망) 통신 사업자 ALI(자동 위치 식별) 데이터베이스에 ELI를 연결합니다.

이러한 작업을 수행하는 방법에 대한 자세한 내용은 배포 설명서에서 [Configure the Location Database을](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) 참조하십시오.

> [!NOTE]
> 중앙 위치 데이터베이스에 추가된 위치는 클라이언트가 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 게시되고 풀의 로컬 저장소로 복제될 때까지 클라이언트에서 사용할 수 없습니다. 자세한 내용은 배포 설명서에서 [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)를 참조하십시오.

이 섹션에서는 위치 데이터베이스를 업데이트 및 유지 관리하기 위한 계획을 세우는 경우 고려해야 할 작업들을 설명합니다.

## <a name="planning-emergency-locations"></a>응급 위치 계획

ELIN 게이트웨이를 사용하는 경우 위치 정보 서비스 데이터베이스를 구민 주소, 건물 내의 특정 위치 및 각 위치에 대해 하나 이상의 ELIN으로 채우게 됩니다. 계획 단계에서는 위치 이름을 지정하는 방법과 LINS를 할당할 방법을 결정하는 것이 좋습니다.

### <a name="planning-location-names"></a>위치 이름 계획

건물 내의  특정 위치를 보유하는 위치 정보 서비스 위치 필드의 최대 길이는 20자(공백 포함)입니다. 이 제한 길이 내에서 다음을 포함합니다.

- 911 발신자 위치를 식별하여 응급 응답자가 구민 주소에 도착할 때 특정 위치를 즉시 찾을 수 있도록 하는 이해하기 쉬운 이름입니다. 이 위치 이름에는 건물 번호, 바닥 번호, wing 지정자, 방 번호가 포함됩니다. 직원에게만 알려진 별명을 피하여 응급 응답자는 잘못된 위치로 이동하게 할 수 있습니다.

- 사용자가 클라이언트가 올바른 위치를 선택했다는 것이 쉽게 확인될 수 있도록 하는 위치 식별자입니다. 이 비즈니스용 Skype 클라이언트는 헤더에 검색된 **위치** 및  도시 필드를 자동으로 연결하고 표시됩니다. 각 위치 식별자에 건물의 주소(예: "1층")를 추가하는 것이 <street number> 좋습니다. 번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.

- 위치가 무선 액세스 지점에 의해 결정되어 대략적인 경우 **[Near]이라는** 단어를 추가할 수 있습니다(예: "1층 1234 근처").

### <a name="planning-elins"></a>ELI 계획

건물 공간을 위치로 나누는 방법을 결정한 후 각 위치에 할당할 LIEN의 수를 결정해야 합니다. 예를 들어 다층 또는 다중테너 건물의 경우 건물의 여러 영역에 서로 다른 비상 영역이 할당될 수 있습니다. 일반적으로 건물의 각 층은 위치로 지정됩니다. 그런 다음 각 위치에는 긴급 통화 중 전화 번호로 사용되는 하나 이상의 ELIEN이 할당됩니다. ELIN에 사용할 수 있는 전화 번호는 PSTN 통신 사업자에 문의합니다. 다음 표에서는 특정 주소의 위치 예를 제공합니다.

**샘플 위치 및 ELIN 할당**

|**건물 영역**|**위치**|**ELIN**|
|:-----|:-----|:-----|
|1층  <br/> |1  <br/> |425-555-0100  <br/> |
|2층  <br/> |2  <br/> |425-555-0111  <br/> |
|3층  <br/> |3   <br/> |425-555-0123  <br/> |

정의하는 위치는 다음 요구 사항을 충족해야 합니다.

- 위치당 최대 영역 및 주소당 위치 수에 따라 현지 및 국가/지역 규정을 준수합니다.

- 긴급 발신자 위치를 쉽게 찾을 수 있을 만큼 구체적입니다.

## <a name="populating-the-location-database"></a>위치 데이터베이스 채우기

다음 질문은 위치 데이터베이스를 채우는 방법을 결정하는 데 도움이 됩니다.

 **위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**

데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?

 **위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**

보조 위치 정보 서비스 옵션을 사용하여 타사 데이터베이스에 연결하면 오프라인 플랫폼을 사용하여 위치를 그룹화하고 관리할 수 있습니다. 이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다. 즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작된 여러 주소를 다른 클라이언트로 비즈니스용 Skype 있습니다. 그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.

위치 정보 서비스와 통합하려면 타사 데이터베이스가 위치 요청/응답 비즈니스용 Skype 서버 따라야 합니다. 자세한 내용은 [Web Service for E911 Support Protocol을 참조합니다.](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd) 보조 위치 정보 서비스를 배포하는 데 대한 자세한 내용은 배포 설명서에서 [Configure a secondary Location Information service in 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 참조하십시오.

위치 데이터베이스를 채우는 방법에 대한 자세한 내용은 배포 설명서에서 [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)을 참조하십시오.

## <a name="maintaining-the-location-database"></a>위치 데이터베이스 유지 관리

위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.

 **어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**

WAP(무선 액세스 지점) 추가, 사무실 다시 사용(서로 다른 스위치 할당 생성) 및 서브넷 확장을 포함하여 위치 데이터베이스를 업데이트해야 하는 몇 가지 시나리오가 있습니다. 각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?

 **SNMP 응용 프로그램을 사용하여 클라이언트 MAC 주소와 비즈니스용 Skype 식별자를 일치시겠습니까?**

SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다. SNMP 응용 프로그램에서 데이터베이스에 포함되지 않은 섀시 IP 주소 또는 포트 ID를 반환하면 위치 정보 서비스에서 클라이언트로 위치를 반환할 수 없습니다.