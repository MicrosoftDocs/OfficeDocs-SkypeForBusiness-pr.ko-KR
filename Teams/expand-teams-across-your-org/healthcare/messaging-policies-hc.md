---
title: Microsoft Teams를 사용하여 의료 조직을 위한 보안 메시징
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 읽은 확인 및 우선 순위 알림을 포함할 수 있는 Microsoft Teams에 대한 보안 메시징 정책을 사용자 지정하는 방법을 배워야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790631"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>의료 조직을 위한 보안 메시징

메시징 정책은 Microsoft Teams에서 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어하는 데 사용하며, 중요한 메시지를 읽을 때 알 수 있는 경우처럼 메시지를 시기적시에 선택하고 처리해야 하는 병원, 의원 또는 의사 사무실과 같은 의료 조직을 위한 보안 메시징의 전체 배포의 일부입니다.

전역(조직 전체 기본값) 정책을 사용하거나 조직 내 사용자에 대해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 사용자 지정 정책을 만든 후 조직의 사용자 또는 사용자 그룹을 할당합니다. 예를 들어 특정 직무 역할이 이러한 기능(아마도 의사 및 간호사만 해당) 및 기타 작업자(예: 재직자 또는 간호사)를 사용하여 더 제한된 기능 집합을 얻을 수 있도록 허용하도록 선택할 수 있습니다. 조직에 필요한 사항을 직접 결정하세요. 여기에 있는 지침은 대부분의 제안 사항입니다.

관리자 자격 증명으로 로그인하고 왼쪽 탐색 창에서 메시징 정책을 선택하여  [Microsoft Teams](https://admin.teams.microsoft.com) 관리 센터에서 정책을 쉽게 관리할 수 있습니다.

 ![메시징 정책 페이지의 스크린샷](../../media/hc-messaging-policy-admin-center.png)

조직의 기존 기본 메시징 정책을 편집하려면 **전역(조직** 전체 기본값)을 클릭한 다음 변경합니다. 새 사용자 지정 메시징 정책을 만들려면 **추가를** 클릭한 다음 설정을 선택합니다. 완료되면 **저장을** 선택 합니다.

![메시징 정책 설정 스크린샷](../../media/hc-messaging-policy.png)

다음 설정은 의료 애플리케이션에 특히 관심이 있으며 의료 필드에 사용되는 사용자 지정 정책을 디자인할 때 고려해야 합니다.

## <a name="read-receipts"></a>읽은 영수증

읽은 확인을 사용하면 채팅 메시지 보낸 사람이 1:1로 받는 사람이 메시지를 읽은 경우를 알 수 있으며 20명 이하의 그룹 채팅을 할 수 있습니다. 이 설정을 사용하여 읽은 확인이 사용자 제어, 모든 사용자에 대한 설정 또는 모든 사용자에 대해 해제하는지 여부를 지정합니다. 메시지 읽은 확인은 메시지가 읽은지 여부를 불확실하게 제거하기 때문에 의료 조직에서 중요합니다.

의료 애플리케이션의 경우 모든 사용자에 대해 **사용자** 제어 또는 **On을 선택 합니다.** 모든 사용자에 대해 **On** 설정을 사용할 때 전체 테넌트에 대한 수신 확인을 설정하는 유일한 방법은 전체 테넌트에 대해 하나의 메시징 정책("전역(전체 기본값)"이라는 기본 정책)만 을 설정하거나 테넌트의 모든 메시징 정책이 수신 확인에 대해 동일한 설정을 사용하는 것입니다. 읽은 확인 기능은 모든 사용자가 기능을 On으로 사용하도록 설정한 **경우 가장 효과적입니다.**

*읽은 확인이 없는 사용 예:* 위험이 높은 환자인 Jakob Roth가 병원에 입원합니다.  Sofia Krause는 이 환자를 담당하는 기본 의료 코디네이터로 다른 전문가를 포함하여 의료 작업자의 IDT(징계 간호사)의 일부로 근무하는 간호사입니다.  Sofia는 다양한 메시징 클라이언트 및 앱을 사용하는 간호사 및 의사 그룹에게 전자 메일 및 기타 메신저 메시지를 보내고, 팀 구성원이 메시지를 읽은 것인지 여부에 대한 응답이나 표시를 읽지 않습니다. angangled 통신 프로세스로 인해 Jakob의 치료가 잘못 처리된 후 입원이 연장됩니다.

*읽은 확인이 있는 사용 예:* 위험이 높은 환자인 Jakob Roth가 병원에 입원합니다.  Sofia Krause는 이 환자를 담당하는 기본 의료 코디네이터로 다른 전문가를 포함하여 의료 작업자의 IDT(징계 간호사)의 일부로 근무하는 간호사입니다.  Sofia는 환자와 함께 진료를 조정하고 긴급 재판을 시작하는 의사 및 다른 간호사 집합과 그룹 채팅을 시작합니다.  간호사와 의사는 진료 조정 프로세스 전체에서 환자의 진료 계획을 커뮤니케이션하고 공동 작업합니다.  중요하고 긴급한 메시지는 1:1 및 그룹 채팅 대화를 통해 전송됩니다. Sofia는 읽은 확인 기능을 사용하여 지원을 요청하는 메시지가 대상 의사 또는 간호사에 의해 배달 및 읽은지 여부를 판단합니다. Jakob의 환자 결과는 최적에 가다가 건강 팀이 원활하게 통신하기 때문에 더 빨리 돌아갑니다.

## <a name="send-urgent-messages-using-priority-notifications"></a>우선 순위 알림을 사용하여 긴급 메시지 보내기

사용자는 채팅 메시지를 다른  사용자에게 보낼 때 긴급한 메시지로 표시될 수 있습니다. 이 기능은 중요한 인시던트에 주의가 필요한 경우 병원 직원이 다른 직원에게 경고하는 데 도움이 됩니다. 일반적인 *중요한* 메시지와 달리 [우선](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) 순위 알림은 최대 20분 동안 또는 받는 사람이 메시지를 선택하고 읽을 때까지 2분마다 사용자에게 알리며, 메시지가 제시간에 처리될 가능성을 극대화합니다.

관리자는 이 정책이 할당된 사용자가 우선 순위 알림을 보낼 수 있는 기능을 설정하거나 해제할 수 있습니다. 이 기능은 기본적으로 설정되어 있습니다. 우선 순위 메시지의 받는 사람은 동일한 메시징 정책을 사용하지 않을 수 있으며 우선 순위 메시지 수신을 사용하지 않도록 설정하는 옵션이 없습니다. 의료 애플리케이션의 경우 일부 사용자에 대해 이 기능을 사용하도록 설정하는 것이 좋습니다. 그러나 어떤 사용자를 결정해야 하는지 결정해야 합니다.

*사용 예:* Sofia Krause는 위험이 높은 환자인 Jakob Roth를 읽습니다. 의사인 Manuela Carstens는 이 환자의 주치의입니다.  Sofia는 Jakob의 재판에서 즉각적인 도움을 요청하는 우선 순위 알림을 사용하여 Manuela로 메시지를 전송합니다.  Manuela의 휴대폰은 메시지를 수신하지만 Manuela는 전화 진동을 느끼지 못하고 회신하지 않습니다. Teams는 Manuela에게 다시 알릴 수 있으며 메시지를 읽을 때까지 지속적으로 다시 알림을 읽습니다. 읽은 확인도 사용하도록 설정되어 있는 경우 Sofia는 Manuela가 응답 방법을 결정하기 전에도 메시지를 Manuela가 읽었다는 것을 알 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Teams에서 메시징 정책 관리](../../messaging-policies-in-teams.md)
- [의료 조직을 위한 Teams 시작](teams-in-hc.md)
