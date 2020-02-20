---
title: 의료 조직을 위한 보안 메시징 시작
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 의료 조직을 위한 보안 메시징 시작
ms.openlocfilehash: efa3b8d046a9f095b6b165de134763b263b68156
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153800"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>의료 조직을 위한 보안 메시징 시작

메시징 정책은 Microsoft 팀에서 사용자에 게 제공 하는 채팅 및 채널 메시징 기능을 제어 하는 데 사용 되며, 병원, clinics 또는 의사 사무실과 같은 의료 조직에 대 한 보안 메시징 전체 배포의 일부입니다. 중요 한 메시지를 읽은 경우를 알고 있는 것 처럼 메시지를 선택 하 고 적시에 처리 하는 것이 중요 합니다.

기본 정책을 사용 하거나 조직의 사용자를 위해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다. 정책을 만든 후에는 조직에서 사용자 또는 사용자 그룹에 게 할당 합니다. 예를 들어 특정 작업 역할 (doctors, nurses에만 해당) 및 기타 작업자 (janitorial 또는 주방 지팡이)만 사용 하 여 제한 된 기능 집합을 얻을 수 있도록 하는 것이 선택 되어 있습니다. 자신을 결정 합니다. 조직의 요구 사항에 대 한 설명은 대부분 추천 사항입니다.

관리자 자격 증명을 사용 하 여 로그인 하 고 왼쪽 탐색 창에서 **메시징 정책을** 선택 하 여 [Microsoft 팀 관리 센터](https://admin.teams.microsoft.com) 에서 정책을 쉽게 관리할 수 있습니다.

 ![메시징 정책 페이지 스크린샷](../../media/messaging-policies-image1.png)

조직의 기존 기본 메시징 정책을 편집 하려면 **전역 (조직 전체 기본값)** 행을 클릭 한 다음 변경 작업을 수행 합니다. 새 사용자 지정 메시징 정책을 만들려면 **새 정책을** 클릭 하 고 설정을 선택 합니다. 완료 되 면 **저장** 을 선택 합니다.

![메시징 정책 설정 스크린샷](../../media/hc-message-policy.png)

다음 설정은 의료 응용 프로그램에 특별히 관심이 있으므로 의료 관련 필드에 사용 되는 사용자 지정 정책을 설계할 때 고려해 야 합니다.

## <a name="read-receipts"></a>읽음 확인

- ![이전 스크린샷](../../media/sfbcallout1.png) 의 설명선을 참조 하는 번호 1의 아이콘 **읽기** 확인 읽음 확인 메시지를 보낸 사람이 1:1 및 그룹 채팅 20 명 이하의 받는 사람이 메시지를 읽었을 때이를 알 수 있습니다. 이 설정을 사용 하 여 읽음 확인을 사용자가 제어할 지, 모든 사람에 대해 또는 모두 끄도록 지정할 수 있습니다. 메시지 읽음 확인은 의료 기관에서 메시지의 읽음 여부에 대 한 uncertainly을 제거 하기 때문에 중요 합니다.

  의료 응용 프로그램의 경우 **사용자가 제어** 또는 **모든 사람에 대해**사용을 선택 합니다. **모든 사용자** 에 대해 확인을 사용 하는 경우 전체 테 넌 트에 대해 확인 메일을 한 개만 설정 ("Global (Org wide default)" 이라는 기본 정책) 하거나 테 넌 트의 모든 메시징 정책에 동일한 확인 설정을 사용 하는 유일한 방법이 있습니다. 읽음 확인 기능은 **모든 사용자**가 기능을 사용 하도록 설정 하는 경우에 가장 효과적입니다.

    읽음 확인 *없이 사용 예제:* 위험도가 높은 Jakob Roth는 병원에 게 참석할 수 있습니다.소피아 Krause는 다른 전문가를 포함 하 여 IDT (disciplinary 팀) 의료 노동자의 일부로 작동 하는 nurse이 환자를 담당 하는 기본 의료 코디네이터로 지정 됩니다.  소피아는 다양 한 메시징 클라이언트 및 앱을 사용 하는 nurses 및 doctors의 그룹에 전자 메일 및 기타 인스턴트 메시지를 보내고, 팀 구성원이 메시지를 읽음 여부에 대 한 응답 또는 표시를 제공 하지 않는 경우가 많습니다. Tangled 통신 프로세스 때문에 Jakob의 투약는 misapplied 되 고 있으며 병원은 계속 해 서 확장 됩니다.

    *읽음 확인을 사용한 사용 예:* 위험도가 높은 Jakob Roth는 병원에 게 참석할 수 있습니다.소피아 Krause는 다른 전문가를 포함 하 여 IDT (disciplinary 팀) 의료 노동자의 일부로 작동 하는 nurse이 환자를 담당 하는 기본 의료 코디네이터로 지정 됩니다.  소피아는 doctors 및 기타 nurses에 대 한 그룹 채팅을 시작 하 고 환자를 사용 하 여 주의를 조정 하 고 긴급 문제 분류를 시작 합니다.Nurses 및 doctors는 의료 조정 프로세스에서 환자 관리 계획을 통해 통신 하 고 공동 작업 합니다.  중요 하 고 긴급 한 메시지는 1:1 및 그룹 채팅 대화를 통해 전송 됩니다. 소피아에서는 읽음 확인 기능을 사용 하 여 요청 지원이 지원 되는 메시지를 전달 하 고 대상 의사 또는 nurses에서 읽도록 할 수 있습니다. Jakob의 환자 결과는 가까이에 있으며, 귀하의 의료 팀이 원활 하 게 통신 하기 때문에 집에 더 빨리 전달 됩니다.

## <a name="priority-notifications"></a>우선 순위 알림

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![이전 스크린샷](../../media/sfbcallout2.png) 의 설명선을 참조 하는 번호 2의 아이콘은 사용자가 다른 사용자에 게 채팅 메시지를 보낼 때 메시지를 "긴급"으로 표시할 수 있는 **우선 순위 알림을 보낼 수 있습니다** . 이 기능을 통해 중요 한 사고에 주의가 필요한 경우 직원 들에 게 서로 알림을 할 수 있습니다. 일반 "중요" 메시지와 달리 우선 순위 알림은 최대 20 분 동안 사용자에 게 메시지를 수신 하 고 읽을 때까지, 메시지가 제때에 처리 될 가능성을 최대화 합니다.

  관리자는이 정책을 할당 한 사용자가 우선 순위 알림을 보내는 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 이 기능은 기본적으로 설정 되어 있습니다. 우선 순위 메시지의 받는 사람에 게는 동일한 메시징 정책이 없을 수 있으며, 우선 순위 메시지를 받을 수 없도록 설정 하는 옵션은 없습니다. 의료 응용 프로그램의 경우 적어도 일부 사용자에 대해이 기능을 사용 하도록 설정 하는 것이 좋지만, 그 중 하나를 결정 해야 합니다.

  *사용 예:* 소피아 Krause는 위험도 환자, Jakob Roth readmitting입니다. Manuela Carstens는이 환자에 대 한 기본 의료입니다.  소피아는 Jakob의 심사에 대 한 즉각적인 도움을 요청 하는 우선 순위 알림을 사용 하 여 Manuela에 게 메시지를 보냅니다.  Manuela의 전화는 메시지를 받지만, Manuela가 전화 진동에 대 한 느낌을 주지 않으며, 응답 하지 않습니다. 팀에서 Manuela에 게 다시 알리고 메시지를 읽을 때까지 지속적으로 다시 알림을 보냅니다. 읽음 확인을 사용 하는 경우 Manuela에서 응답 방법을 결정 하기 전에는 Manuela에서 메시지를 소피아 알 수 있습니다.

## <a name="related-topics"></a>관련 주제

- [팀에서 메시징 정책 관리](../../messaging-policies-in-teams.md)
- [의료 조직을 위한 Teams 시작](teams-in-hc.md)
