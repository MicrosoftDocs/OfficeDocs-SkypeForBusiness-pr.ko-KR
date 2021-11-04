---
title: SIP 트렁크 서비스 공급자의 위치 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: SIP 트렁크 공급자를 사용하는 E9-1-1 배포를 위해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 4bc74933623f1a435288246ac695c9545c8606d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751547"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>SIP 트렁크 서비스 공급자의 위치 비즈니스용 Skype 서버

SIP 트렁크 공급자를 사용하는 E9-1-1 배포를 위해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.

네트워크 비즈니스용 Skype 서버 자동으로 클라이언트를 찾도록 구성하려면 위치 정보 서비스 데이터베이스를 네트워크 와이어맵으로 채우고 위치를 게시하거나 올바른 매핑이 이미 포함된 외부 데이터베이스에 연결해야 합니다. 이 프로세스의 일부로, E9-1-1 서비스 공급자를 통해 구/군/시 주소를 확인해야 합니다. 자세한 내용은 배포 설명서에서 [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)을 참조하십시오.

위치 정보 서비스 데이터베이스를 건물의 구/군/시 주소와 특정 주소로 구성된 ERL(비상 응답 위치)로 채울 수 있습니다. 건물 내의 특정 위치인 위치 정보 서비스 **위치** 필드의 최대 길이는 20자(공백 포함)입니다. 이 제한 길이 내에서 다음을 포함합니다.

- 119 발신자 위치를 식별하는 알기 쉬운 이름으로 비상 응답자가 구/군/시 주소에 도착하자 마자 특정 위치를 찾을 수 있도록 도와줍니다. 이 위치 이름에는 건물 번호, 층, 윙 지정자, 호수 등이 포함될 수 있습니다. 직원만 알고 있는 별칭은 가급적 사용하지 마십시오. 이러한 이름은 비상 응답자를 잘못된 위치로 이동시킬 수 있습니다.

- 사용자가 해당 클라이언트가 올바른 위치를 선택했다는 비즈니스용 Skype 식별자입니다. 이 비즈니스용 Skype 클라이언트는 헤더에 검색된 **위치** 및  도시 필드를 자동으로 연결하고 표시됩니다. 각 위치 식별자에 건물의 주소(예: "1층")를 추가하는 것이 <street number> 좋습니다. 번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.

- 위치가 무선 액세스 지점에 의해 결정되어 대략적인 경우 **[Near]이라는** 단어(예: "Near 1st Floor 1234")를 추가할 수 있습니다.

> [!NOTE]
> 중앙 위치 데이터베이스에 추가된 위치는 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 게시하고 풀의 로컬 저장소로 복제될 때까지 클라이언트에서 사용할 수 없습니다. 자세한 내용은 배포 설명서에서 [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)를 참조하십시오.

다음 섹션에서는 위치 데이터베이스를 채우고 유지 관리할 때 고려해야 할 사항에 대해 설명합니다.

## <a name="populating-the-location-database"></a>위치 데이터베이스 채우기

다음 질문은 위치 데이터베이스를 채우는 방법을 결정하는 데 도움이 됩니다.

 **위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**

데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?

 **위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**

보조 위치 정보 서비스 옵션을 사용하여 타사 데이터베이스에 연결하면 오프라인 플랫폼을 사용하여 위치를 그룹화하고 관리할 수 있습니다. 이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다. 즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작된 여러 주소를 다른 클라이언트로 비즈니스용 Skype 있습니다. 그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.

위치 정보 서비스와 통합하려면 타사 데이터베이스가 Lync Server 위치 요청/응답 schema를 따라야 합니다. 자세한 내용은 ["[MS-E911WS]: E911용 웹 서비스 지원 프로토콜 사양"을 참조하세요.](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd) 보조 위치 정보 서비스를 배포하는 데 대한 자세한 내용은 배포 설명서에서 [Configure a secondary Location Information service in 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 참조하십시오.

위치 데이터베이스를 채우는 방법에 대한 자세한 내용은 배포 설명서에서 [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)을 참조하십시오.

## <a name="maintaining-the-location-database"></a>위치 데이터베이스 유지 관리

위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.

 **어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**

WAP 추가, 사무실 케이블 재연결(스위치 할당이 달라짐) 및 서브넷 확장 등을 포함하여 위치 데이터베이스를 업데이트해야 하는 몇 가지 시나리오가 있습니다. 각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?

 **SNMP 응용 프로그램을 사용하여 Lync 클라이언트 MAC 주소를 포트 및 스위치 식별자와 일치시키시겠습니까?**

SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다. SNMP 응용 프로그램에서 데이터베이스에 포함되지 않은 섀시 IP 주소 또는 포트 ID를 반환하면 위치 정보 서비스에서 클라이언트로 위치를 반환할 수 없습니다.