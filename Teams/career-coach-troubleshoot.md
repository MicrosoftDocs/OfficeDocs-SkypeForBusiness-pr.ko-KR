---
title: Microsoft Teams의 경력 코치 문제 해결
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams용 경력 코치의 일반적인 문제를 해결하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242452"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Microsoft Teams의 경력 코치 문제 해결

이 문서는 Microsoft Teams의 경력 코치 문제를 해결해야 하는 교육 IT 관리자를 위한 것입니다.

다음은 IT 관리자가 경력 코치와 함께 수행할 수 있는 일반적인 문제 및 해결 단계입니다.

## <a name="missing-required-configuration-data"></a>필수 구성 데이터 누락

커리어 코치 환경에 "커리어 코치가 현재 곧 사용할 수 있도록 설정되고 있습니다."가 표시되면 **필요한 모든 구성 데이터가 추가되지 않았습니다**.

기관에 [LinkedIn 연결](career-coach-set-up-steps.md#linkedin-connection-required) 이 완전히 구성되어 있어야 합니다.

[경력 코치 구성 상태를](career-coach-set-up-steps.md#configuration-status) 참조하여 완료해야 하는 설정을 확인합니다.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>과정 카탈로그 또는 학습 데이터 필드의 형식이 잘못되었습니다.

과정 카탈로그 및 연구 분야의 CSV에는 필수 형식과 최대 크기가 18MB입니다.

적절한 구성을 보장하려면 경력 코치 [과정 카탈로그 문서 스키마](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) 및 [학습 문서 스키마의](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) 경력 코치 필드를 참조하세요.

또한 성공적인 처리를 위해 과정 카탈로그 파일에 15,000개 이상의 행이 없어야 합니다.

## <a name="missing-fields-in-career-coach-settings-pages"></a>경력 코치 설정 페이지에서 누락된 필드

경력 코치 설정 페이지에는 필수 필드가 있습니다. 필요한 필드가 완료되지 않으면 페이지가 제출되지 않습니다.

경고 메시지가 표시되지 않을 수 있으며 페이지가 제출되지 않습니다.

페이지 맨 위에 녹색 배너가 표시되면 제출에 성공합니다.

## <a name="setup-policy-changes-arent-complete"></a>설정 정책 변경이 완료되지 않음

경력 코치가 사용자를 위해 Microsoft Teams에 표시되지 않으면 설정 정책 변경 내용이 아직 적용되지 않았을 수 있습니다. 설정 정책 변경 내용이 적용될 때까지 Microsoft Teams의 사용자에 대해 경력 코치가 설치 및 고정되지 않습니다. 정책 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.

그러나 경력 코치는 Microsoft Teams 앱 스토어에서 직접 설치할 수 있습니다.

- 사용자가 Microsoft Teams 앱 스토어에서 경력 코치를 찾을 수 없는 경우 앱 사용 권한 정책을 검토하고 경력 코치가 차단된 앱이 아닌지 확인합니다.
- 경력 코치는 Microsoft 앱이며 권한 정책별로 Microsoft 앱을 허용하는 것이 가장 좋습니다. [권한 정책 구성](teams-app-permission-policies.md)에 대해 자세히 알아봅니다.

## <a name="career-coach-initialization-isnt-complete"></a>경력 코치 초기화가 완료되지 않음

다음 오류가 발생할 수 있습니다. "앱 설정을 검색할 수 없습니다. 다시 시도하십시오. 문제가 계속되면 Microsoft 고객 지원에 문의하세요."

[경력 코치 설정 페이지에서](career-coach-set-up-steps.md#career-coach-settings-status) **서비스 프로비저닝 상태를** 확인합니다.

테넌트가 아직 초기화되고 있는 경우 15분 동안 기다렸다가 다시 시도하세요. 그래도 오류가 발생하면 지원 티켓을 엽니다.
