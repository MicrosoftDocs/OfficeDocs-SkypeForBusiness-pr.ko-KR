---
title: 2016년 8월의 응급 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: 위치 검색 및 통화 라우팅을 포함하여 비즈니스용 Skype 서버 Enterprise Voice E9-1-1(Enhanced 9-1-1) 서비스에 대해 자세히 알아보습니다.
ms.openlocfilehash: 4f75dcce3bc8de2e8e4f806c1c571c2e7cad1afe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844161"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>2016년 8월의 응급 비즈니스용 Skype 서버

위치 검색 및 통화 라우팅을 포함하여 비즈니스용 Skype 서버 Enterprise Voice E9-1-1(Enhanced 9-1-1) 서비스에 대해 자세히 알아보습니다.

비즈니스용 Skype 서버 배포의 일부로 미국 내에서 E9-1-1(Enhanced 9-1-1) 서비스를 Enterprise Voice 있습니다. E9-1-1은 구/군/시 주소와 더 구체적인 기타 위치 정보(예: 사무실 건물 및 다가구 시설에서 거는 전화의 경우 층 번호)로 구성되는 ERL(Emergency Response Location)과 9-1-1 전화를 연결하는 응급 발송 기능입니다. PSAP(Public Safety Answering Point)는 제공된 ERL을 사용하여 응급 상황에 처한 발신자에게 최초 대응 인원을 즉시 파견할 수 있으며, 모호하거나 잘못된 위치로 대응 인원을 실수로 파견할 위험을 줄일 수 있습니다.

> [!NOTE]
> 비즈니스용 Skype 서버 클라이언트에 대해 여러 긴급 번호 구성을 지원할 수 있습니다. 자세한 내용은 [Plan for multiple emergency numbers in 비즈니스용 Skype 서버.](multiple-emergency-numbers.md)

> [!NOTE]
> 비즈니스용 Skype 서버 기능으로는 통화 Enterprise Voice, 응급 서비스(E9-1-1) 및 미디어 우회의 세 가지 고급 보안 기능이 있습니다. 이러한 세 기능에 공통적인 계획 정보의 개요는 에서 고급 Enterprise Voice 기능에 대한 네트워크 설정을 [비즈니스용 Skype 서버.](network-settings-for-advanced-features.md)

비즈니스용 Skype 서버 클라이언트 및 Lync 전화 장치로부터의 E9-1-1(Enhanced 9-1-1) 통화를 비즈니스용 Skype 지원합니다. E9-1-1에 비즈니스용 Skype 서버 구성할 때 비즈니스용 Skype 또는 Lync 전화 Edition에서 걸려오는 긴급 통화에는 위치 정보 서비스 데이터베이스의 ERL(Emergency Response Location) 정보가 포함됩니다. ERL은 주소와 사무실 건물 또는 복합 시설 내의 위치를 더 정확히 식별하는 데 도움이 되는 기타 정보로 구성됩니다. 사용자가 긴급 통화를 할 때 비즈니스용 Skype 서버 통화 오디오를 위치 및 콜백 정보와 함께 중재 서버를 통해 E9-1-1 서비스 공급자로 라우팅합니다. E9-1-1 서비스 공급자는 발신자의 주소를 사용하여 발신자의 위치에 서비스를 제공하는 PASP(Public Safety Answering Point)로 통화를 라우팅하고 PSAP가 발신자 ERL을 조회하는 데 사용하는 ESQK(Emergency Service Query Key)를 함께 전송합니다.

비즈니스용 Skype 서버 E9-1-1 서비스 공급자로 긴급 통화를 라우팅하는 두 가지 방법을 지원할 수 있습니다.

- 적격 E9-1-1 서비스 공급자에 대한 SIP(Session Initiation Protocol) 트렁크 연결

- PSTN(공중 전화망) 기반 E9-1-1 서비스 공급자에 대한 ELIN(Emergency Location Identification Number) 게이트웨이

SIP 트렁크 E9-1-1 서비스 공급자를 사용하는 경우 위치 정보 서비스 데이터베이스에 ERL을 추가한 다음 E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드)에 대해 위치의 유효성을 검사합니다. E9-1-1 서비스 공급자가 위치 정보가 없는 통화를 받거나 MSAG에 대해 유효성을 검사하지 않은 위치가 있는 경우 E9-1-1 서비스 공급자는 통화를 지역/지역 응급 통화 응답 센터(ECRC)로 라우팅합니다. 이 센터는 가능한 경우 발신자 위치를 구두로 받는 특수 교육을 받은 직원으로 배치됩니다.  에서 호출을 적절한 PSAP로 수동으로 라우팅합니다. 일부 SIP 트렁크 E9-1-1 서비스 공급자는 어떤 이유로든 SIP 트렁크가 실패할 경우 9-1-1 통화를 라우팅하는 대체 방법을 제공하는 ECRC에 PSTN DID(Direct Inward Dialing) 번호를 고객에게 제공합니다.

고정된 위치가 있는 TDM(시간 디비전 다중화) 및 IP 기반 PBX(Private Branch Exchange) 전화와 달리 비즈니스용 Skype 끝점은 모바일이 될 수 있습니다. E9-1-1 기능을 배포할 때 비즈니스용 Skype 서버 발신자 위치에 상관없이 발신자 위치를 제공하는 PSAP로 긴급 통화를 라우팅할 수 있습니다. 예를 들어 사용자의 주 사무실이 워싱턴주 레드몬드에 있지만 사용자가 칸자스 Wichita, SIP 트렁크 또는 PSTN 기반 E9-1-1 서비스 공급자가 통화를 레드몬드의 PSAP가 아닌 Wichita의 PSAP로 라우팅합니다.

ELIN 게이트웨이를 사용하는 경우 위치 정보 서비스 데이터베이스에도 ERL을 추가하지만 각 위치에 대한 ELIN 번호도 포함합니다. 긴급 통화 중에는 ELIN 번호가 긴급 발신 번호가 됩니다. 그러면 PSTN 통신 회사에서 ELIN을 ALI(Automatic Location Identification) 데이터베이스에 업로드했는지 확인해야 합니다.

> [!NOTE]
> 비즈니스용 Skype 연결된 아날로그 장치는 위치 정보 서비스에서 위치 정보를 수신하거나 위치를 E9-1-1 서비스 공급자로 전송할 수 없습니다.

 SIP 트렁크 E9-1-1 서비스 공급자 옵션을 사용하며 아날로그 전화에서 E9-1-1을 지원해야 하는 경우에는 두 가지 옵션이 있습니다.

- **기존 PS-ALI 옵션** 아날로그 전화가 배포되는 각 사이트에 로컬 PSTN 게이트웨이가 있는 경우 각 아날로그 전화에 DID가 있는 경우 PS-ALI(Private Switch/Automatic Location Identification) 서비스 공급자를 사용하여 아날로그 장치의 위치를 직접 프로비전할 수 있습니다. 이 경우 특수하게 만든 비즈니스용 Skype 음성 정책을 구성하고 아날로그 장치 연락처 개체에 할당하여 해당 전화의 E9-1-1 통화가 E9-1-1 서비스 공급자 SIP 트렁크로 통화를 라우팅하는 대신 로컬 게이트웨이를 통해 사이트를 제공하는 PSTN 공급자로 직접 라우팅하도록 합니다. 긴급 통화가 걸려오면 PSTN 트렁크와 연결된 PS-ALI 공급자의 데이터베이스가 각 아날로그 전화의 DID를 실제 위치에 매핑하고 이 위치를 PSAP에 제공합니다. 전화가 다른 ERL로 이동될 때마다 PS-ALI 서비스 공급자에서 이러한 레코드가 업데이트되어야 합니다.

- **E9-1-1 서비스 공급자 옵션** E9-1-1 서비스 공급자가 지원하는 경우 아날로그 전화 DID 및 해당 ERL을 E9-1-1 서비스 공급자에 등록할 수 있습니다. 공급자가 PIDF-LO 비즈니스용 Skype 서버 없는 공급자로부터 전화를 받는 경우 공급자는 발신자 DID 번호에 데이터베이스 일치가 있는지 볼 수 있습니다. 공급자는 데이터베이스에서 검색된 ERL을 사용하여 긴급 통화를 올바른 PSAP로 자동으로 라우팅할 수 있으며 PSAP는 아날로그 장치의 DID 및 발신자가 발신자 위치를 검색할 수 있는 ESQK 레코드를 받게 됩니다.

ELIN 게이트웨이 옵션을 사용하며 아날로그 장치에서 E9-1-1을 지원해야 하는 경우에는 위의 첫 번째 옵션에 설명되어 있는 것처럼 PS-ALI 서비스 공급자를 통해 직접 아날로그 장치의 위치를 프로비전할 수 있습니다.

E9-비즈니스용 Skype 서버 관점에서 E9-1-1 프로세스는 다음 두 단계로 구분될 수 있습니다.

- 1단계: 위치 얻기

- 2단계: 긴급 통화를 E9-1-1 서비스 공급자로 라우팅

이 섹션에서는 이 두 단계의 작동 방식에 대해 설명합니다.

클라이언트 위치를 자동으로 감지하도록 인프라를 구성하려는 경우 먼저 발신자를 위치에 매핑하는 데 사용할 네트워크 요소를 결정해야 합니다. 가능한 옵션에 대한 자세한 내용은 [Define the network elements used to determine location in 비즈니스용 Skype 서버.](network-location.md)

## <a name="acquiring-a-location"></a>위치 검색

비즈니스용 Skype 서버 E9-1-1 배포에서 내부적으로 연결된 각 비즈니스용 Skype 또는 Lync 전화 Edition 클라이언트는 자체 위치를 적극적으로 획득합니다. SIP 등록 후 클라이언트는 자체적으로 알고 있는 모든 네트워크 연결 정보를 위치 정보 서비스에 대한 위치 요청으로 제공합니다. 이 정보는 복제된 데이터베이스에서 지원되는 웹 SQL Server 제공합니다. 각 중앙 사이트 풀에는 네트워크 정보를 사용하여 해당 레코드에서 일치하는 위치를 쿼리하는 위치 정보 서비스가 있습니다. 일치하는 위치가 있는 경우 위치 정보 서비스는 클라이언트에 위치를 반환합니다. 일치하는 위치가 없는 경우 위치를 수동으로 입력하라는 메시지가 표시될 수 있습니다(위치 정책 설정에 따라 다를 수 있습니다). 위치 데이터는 PIDF-LO(Presence Information Data Format Location Object)라는 IETF(Internet Engineering Task Force) 표준 XML 형식으로 클라이언트로 다시 전송됩니다.

비즈니스용 Skype 클라이언트는 긴급 통화의 일부로 PIDF-LO 데이터를 포함하며, 이 데이터는 E9-1-1 서비스 공급자가 적절한 PSAP를 결정하고 올바른 ESQK와 함께 해당 PSAP로 통화를 라우팅하는 데 사용되어 PSAP 디스패처가 발신자 위치를 얻을 수 있습니다.

다음 다이어그램은 비즈니스용 Skype 클라이언트가 위치를 획득하는 방법을 보여줍니다(타사 클라이언트 MAC 주소 기반 위치 방법 제외).

![클라이언트가 위치 다이어그램을 획득하는 방법](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

클라이언트가 위치를 확보하기 위해서는 다음 단계가 수행되어야 합니다.

1. 관리자는 네트워크 와이어맵(다양한 유형의 네트워크 주소를 해당 ERL(Emergency Response Locations)에 매핑하는 표)으로 위치 정보 서비스 데이터베이스를 채우게 됩니다.

2. SIP 트렁크 E9-1-1 서비스 공급자를 사용하는 경우 관리자는 E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드) 데이터베이스에 대해 ERL의 주소 부분이 올바른지 확인합니다. ELIN 게이트웨이를 사용하는 경우에는 관리자가 PSTN 통신 회사에서 ELIN을 ALI(Automatic Location Identification) 데이터베이스에 업로드했는지 확인합니다.

3. 등록하는 동안 또는 네트워크 변경이 발생할 때마다 내부에 연결된 클라이언트는 클라이언트가 검색한 네트워크 주소가 포함된 위치 요청을 위치 정보 서비스로 전송합니다.

4. 위치 정보 서비스는 게시된 레코드에 대해 위치를 쿼리하고 일치하는 레코드가 발견된 경우 PIDF-LO 형식으로 클라이언트에 ERL을 반환합니다.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>SIP 트렁크를 사용하여 E9-1-1 통화 라우팅

SIP 트렁크를 사용하여 적격 E9-1-1 서비스 공급자에 연결하는 것은 E9-1-1을 배포하는 데 사용할 수 있는 한 가지 방법입니다. ELIN 게이트웨이를 사용하여 공중 전화망(PSTN) 기반 E9-1-1 서비스 공급자에 연결하는 방법에 대한 자세한 내용은 [Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway)을 참조하십시오.

다음 다이어그램은 SIP 트렁크 및 적격 E9-1-1 서비스 공급자를 사용할 때 긴급 통화가 비즈니스용 Skype 서버 PSAP(Public Safety Answering Point)로 라우팅되는 방법을 보여줍니다.

**SIP 트렁크를 통한 E9-1-1 통화 라우팅**

![Lync Server에서 PSAP로의 긴급 통화 라우팅](../../media/Plan_LyncServer_E911_CallRouting.jpg)

호환되는 클라이언트에서 긴급 통화가 걸려오면 비즈니스용 Skype 서버:

1. 위치, 발신자 콜백 번호 및 (선택 사항) 알림 URL 및 전화 회의 콜백 번호가 포함된 SIP INVITE는 비즈니스용 Skype 서버.

2. 비즈니스용 Skype 서버 번호와 일치하고 해당 위치 정책에 정의된 **PSTN** 사용 값에 따라 통화를 중재 서버로 라우팅하고 SIP 트렁크를 통해 E9-1-1 서비스 공급자로 라우팅합니다.

3. E9-1-1 서비스 공급자는 통화와 함께 제공된 위치에 따라 긴급 통화를 올바른 PSAP로 라우팅합니다. 클라이언트가 긴급 통화와 함께 확인된 ERL(Emergency Response Location)을 포함하는 경우 공급자는 통화를 적절한 PSAP로 자동으로 라우팅합니다. 사용자가 수동으로 위치를 입력한 경우에는 먼저 ECRC(Emergency Call Response Center)에서 발신자와 구두로 위치가 정확한지 확인한 후 긴급 통화를 PSAP로 라우팅합니다.

4. 알림에 대한 위치 정책을 구성한 경우 하나 이상의 조직의 보안 담당자에게 긴급 알림 인스턴트 비즈니스용 Skype 전송됩니다. 이 메시지는 항상 보안 담당자의 화면에 표시하고 발신자 이름, 전화 번호, 시간 및 위치를 포함하며, 보안 담당자가 인스턴트 메시지 또는 음성을 사용하여 긴급 발신자에 신속하게 응답할 수 있도록 합니다.

5. 회의용 위치 정책을 구성했으며 E9-1-1 서비스 공급자가 이 정책을 지원하는 경우에는 단방향 또는 양방향 오디오를 사용하여 내부 보안 데스크와의 전화 회의가 이루어집니다.

6. 통화가 중간에 끊기면 PSAP가 콜백 번호를 사용하여 발신자와 직접 연결합니다.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>ELIN 게이트웨이를 사용하여 E9-1-1 통화 라우팅

Unified Communications Open Interoperability Program의 일부 파트너는 자격이 있는 E9-1-1 서비스 공급자에 대한 SIP 트렁크 연결의 대안으로 사용할 수 있는 자격이 있는 ELIN(Emergency Location Identification Number) 지원 게이트웨이를 제공합니다. ELIN 게이트웨이는 PSTN(공중 전화망) 기반의 E9-1-1 서비스에 대한 ISDN 또는 CAMA(Centralized Automatic Message Accounting) 연결을 지원합니다. ELIN 게이트웨이 및 설명서 링크를 제공하는 파트너에 대한 자세한 내용은 [Microsoft Lync에](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 대해 자격을 갖춘 인프라 및 Lync에 대한 전화 통신 인프라를 [비즈니스용 Skype.](../../../SfbPartnerCertification/certification/infra-gateways.md)

E9-1-1 서비스 공급자에 대한 SIP 트렁크 연결과 마찬가지로 ELIN 게이트웨이는 긴급 통화를 발신자가 가장 적합한 PSAP(Public Safety Answering Point)로 라우팅하는 수단도 제공하지만 이러한 게이트웨이는 위치 식별자로 ELIN을 사용하게 됩니다. 조직의 각 ERL(Emergency Response Location)에 대한 ELIIN을 정의합니다(자세한 내용은 [Manage locations for ELIN gateways in 비즈니스용 Skype 서버](elin-gateways.md)참조).

긴급 통화에 ELIN 게이트웨이를 사용하는 경우 SIP 트렁크 연결에 비즈니스용 Skype 서버 동일한 E9-1-1 인프라를 사용할 수 있습니다. 즉, 위치 정보 서비스 데이터베이스는 비즈니스용 Skype 클라이언트에 위치를 제공하며, 위치 정책은 기능을 사용할 수 있으며 라우팅을 정의합니다. 그러나 ELIN 게이트웨이를 사용할 경우 위치 정보 서비스 데이터베이스에 ELIN을 추가하고 PSTN 통신 사업자에서 ALI(자동 위치 식별) 데이터베이스에 업로드해야 합니다.

클라이언트가 비즈니스용 Skype 서비스에서 위치를 얻은 경우 위치에 ELIN이 포함됩니다. 긴급 통화 중 ELIN에는 ELIN 게이트웨이에 전송된 위치가 포함됩니다. ELIN 게이트웨이는 통화를 긴급 통화로 식별하고 통화 당사자의 번호를 ELIN으로 전환합니다. 그런 후 ELIN 게이트웨이는 호출 번호로 ELIN을 사용해서 통화를 PSTN으로 라우팅합니다. PSTN E9-1-1 공급자는 MSAG(Master Street Address Guide) 데이터베이스의 부속 데이터베이스인 ALI 데이터베이스에서 ELIN을 조회합니다. 그런 후 PSTN은 ALI 조회를 기반으로 가장 적합한 PSAP로 통화를 전송하고, PSAP는 ALI 조회를 기반으로 첫 번째 응답자를 발신자의 위치로 보냅니다. 호출 중인 번호는 콜백을 위해 미리 정의된 일정 기간 동안 ELIN 게이트웨이에 캐시로 저장됩니다. 콜백 중에는 PSAP가 ELIN 게이트웨이에 연결하여 발신자의 DID(direct inward dialing) 번호를 얻기 위해 ELIN으로 전환합니다.

ELIN 게이트웨이는 조직 내 네트워크 내부에서만 긴급 통화를 지원합니다. 네트워크 외부로부터의 긴급 통화는 지원하지 않습니다.

> [!NOTE]
> 긴급 통화를 위해 SIP 트렁크 연결을 사용하는 방법에 대한 자세한 내용은 [Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk)을 참조하십시오.

다음 다이어그램은 ELIN 게이트웨이를 사용할 때 긴급 통화가 비즈니스용 Skype 서버 PSAP로 라우팅되는 방법을 보여줍니다.

**ELIN 게이트웨이로 E9-1-1 통화 라우팅**

![응급 서비스에 대한 통화가 중재 서버를 통과한 다음 응급 서비스 공급자로 이동하는 방법을 보여줍니다. 이 경우 선택적으로 인시던트 보안으로 전송된 IM 및/또는 원래 발신자에 대한 전화가 있을 수 있습니다.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. 위치, 발신자 콜백 번호 및 (선택 사항) 알림 URL 및 전화 회의 콜백 번호가 포함된 SIP INVITE는 위치로 비즈니스용 Skype 서버.

2. 비즈니스용 Skype 서버 번호와 일치한 다음 해당 위치 정책에 정의된 **PSTN** 사용 값에 따라 통화를 중재 서버로 라우팅하고 통화를 해당 위치에서 ELIN 게이트웨이로 라우팅합니다.

3. ELIN 게이트웨이는 ISDN 또는 CAMA 트렁크를 통해 통화를 PSTN으로 라우팅합니다.

4. PSTN은 통화를 긴급 통화로 식별하고 이를 네트워크에서 E9-1-1 선택적 라우터로 라우팅합니다. E9-1-1 선택적 라우터는 지리적 위치 정보를 가져오기 위해 ALI 데이터베이스에서 발신자의 번호를 조회합니다. E9-1-1 선택적 라우터는 ALI 데이터베이스에서 검색된 위치 정보를 기반으로 가장 적합한 PSAP에 통화를 전송합니다.

5. 알림에 대한 위치 정책을 구성한 경우 하나 이상의 조직의 보안 담당자에게 긴급 알림 인스턴트 비즈니스용 Skype 전송됩니다. 이 메시지는 항상 보안 담당자의 화면에 표시하고 발신자 이름, 전화 번호, 시간 및 위치를 포함하며, 보안 담당자가 인스턴트 메시지 또는 음성을 사용하여 긴급 발신자에 신속하게 응답할 수 있도록 합니다.

6. 통화가 중간에 끊어지면 PSAP는 ELIN을 사용해서 발신자에게 직접 연락합니다. ELIN 게이트웨이는 발신자의 DID를 위해 ELIN을 전환합니다.