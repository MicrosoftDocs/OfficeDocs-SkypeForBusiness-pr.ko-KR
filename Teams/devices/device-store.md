---
title: Teams 디바이스 저장소
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: rahulimi
ms.topic: article
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
description: Teams 관리 센터 디바이스 저장소에서 디바이스를 찾아보고 구매하는 방법을 알아봅니다.
ms.openlocfilehash: 9e555cd0f389c8158e66b824183a1038fc11ce04
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240717"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Teams 디바이스 저장소에서 디바이스 구매

Teams 관리 센터의 디바이스 저장소를 사용하면 Microsoft Teams용으로 인증된 디바이스를 찾아보고, 구매하고, 프로비전할 수 있습니다.  

 Teams 관리 센터에서 디바이스 저장소를 사용하려면 **디바이스 > 스토어** 로 이동합니다.

## <a name="requirements"></a>요구 사항

디바이스 저장소를 사용하려면 전역 관리자 또는 Teams 관리자여야 합니다.

## <a name="browse-the-store"></a>스토어 찾아보기

디바이스 저장소에는 헤드셋, 웹 카메라 및 Teams 디바이스(예: Teams 룸, 책상 전화 및 Teams 디스플레이)를 포함하여 Teams용으로 인증된 모든 디바이스가 포함되어 있습니다. 정렬, 필터링 또는 검색하여 조직에 필요한 디바이스를 찾을 수 있습니다.

## <a name="purchase-devices"></a>디바이스 구매

디바이스 스토어에서 디바이스를 구매하면 Microsoft 타사 처리 파트너인 UnifiedCommunications.com 배송 및 배달을 포함한 결제 및 처리가 처리됩니다.  

신용 카드 또는 구매 주문으로 결제할 수 있습니다. 주문 결제를 구매하려면 주문 처리 공급자를 일회성으로 설정해야 합니다.

모든 주문은 배송 후 최대 30일까지 반환할 수 있습니다.

## <a name="data-handling-and-sharing"></a>데이터 처리 및 공유

Teams 디바이스 저장소는 Teams 관리 센터에서 구매할 수 있도록 UnifiedCommunications.com 사용자 및 테넌트 GUID를 포함한 기본 사용자 및 회사 정보를 공유해야 합니다.

데이터 공유는 기본적으로 꺼져 있습니다. 사용하도록 설정하려면 Teams 디바이스 저장소로 이동하여 설정 아이콘을 선택하고 설정을 켭니다.  

이 설정이 꺼져 있으면 데이터가 공유되지 않으며 Teams 디바이스 저장소를 검색할 수 있지만 구매할 수는 없습니다. 설정이 설정된 동안 처리 공급자와 수집 및 공유된 데이터는 개인 정보 취급 방침에 지정된 대로 처리됩니다.

## <a name="order-tracking-and-history"></a>주문 추적 및 기록

사용자 및 조직의 다른 관리자가 주문한 모든 주문이 포함된 **Store > 주문 기록** 으로 이동하여 주문 기록을 볼 수 있습니다. 주문 기록에는 주문의 배송 상태도 포함됩니다. 주문 추적, 반품 또는 환불에 대한 질문은 UnifiedCommunications.com 문의하세요. 해당 연락처 정보는 주문 기록 페이지에서 사용할 수 있습니다.

Teams 디바이스 저장소에 배치된 주문 및 연결된 모든 데이터는 테넌트 주문 및 테넌트 데이터로 분류됩니다.

## <a name="provision-devices"></a>디바이스 프로비전

원격 프로비저닝을 지원하는 디바이스를 구매하면 디바이스가 배송될 때 해당 디바이스의 MAC 주소가 Teams 관리 센터에 자동으로 추가됩니다. 주문 및 배송 시기에 따라 MAC 주소가 Teams 관리 센터에 표시되는 데 약 5일이 걸릴 수 있습니다.

디바이스가 배달되면 [원격 프로비전 디바이스](remote-provision-remote-login.md#generate-a-verification-code) 를 참조하여 프로비전 및 로그인 프로세스를 완료합니다.
