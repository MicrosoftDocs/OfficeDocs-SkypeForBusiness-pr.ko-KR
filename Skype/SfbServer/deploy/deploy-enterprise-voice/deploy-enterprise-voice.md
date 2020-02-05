---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '요약: 중앙 사이트의 비즈니스용 Skype Server에 대 한 엔터프라이즈 음성을 배포 하는 방법을 알아봅니다.'
ms.openlocfilehash: 1b1b1d0f79d1730bd491314f4f4e97b43b0acb62
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767551"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 엔터프라이즈 음성 배포

**요약:** 중앙 사이트의 비즈니스용 Skype 서버에 엔터프라이즈 음성을 배포 하는 방법에 대해 알아봅니다.

이 항목을 사용 하 여 중앙 사이트에서 엔터프라이즈 음성을 배포 합니다. 지점 사이트에서 엔터프라이즈 음성을 배포 하려면 [분기 사이트 배포](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)로 건너뛰십시오.

이 섹션에는 각 프런트 엔드 서버 또는 스탠더드 버전 서버에서 중재 서버를 collocated 하는 배포에 대 한 절차와 함께, 독립 실행형 중재 서버 풀을 사용 하 여 배포 하기 위한 절차가 포함 되어 있습니다. 배포 마법사가 각 프런트 엔드 서버 또는 Standard Edition 서버에서 중재 서버를 찾는 토폴로지를 정의 하 고 게시 하는 경우 다음 콘텐츠를 건너뛸 수 있습니다. 프런트 엔드 서버 풀 또는 Standard Edition Server 용 파일을 설치할 때 중재 서버:
## <a name="in-this-section"></a>이 섹션의

- [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건](enterprise-voice-security.md)

- [비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포](deploy-a-mediation-server.md)

- [비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의](define-a-gateway.md)

- [비즈니스용 Skype 서버의 토폴로지 작성기에 추가 trunks 정의](define-additional-trunks.md)

- [비즈니스용 Skype 서버에서 중재 서버용 파일 설치](install-mediation-server.md)

- [비즈니스용 Skype 서버에서 trunks 구성](configure-trunks.md)

- [비즈니스용 Skype 서버에서 발신자 ID 프레젠테이션의 번역 규칙 만들기 또는 수정](caller-id-presentation-rules.md)

- [비즈니스용 Skype 서버에서 호출 된 ID 프레젠테이션에 대 한 번역 규칙 만들기 또는 수정](called-id-presentation-rules.md)

- [비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정](normalization-rules.md)

- [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](dial-plans.md)

- [비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](voice-and-pstn.md)

- [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화](enable-users-for-enterprise-voice.md)

- [비즈니스용 Skype 서버에서 고급 엔터프라이즈 음성 기능 배포](deploy-advanced-enterprise-voice-features.md)

- [비즈니스용 Skype에서 통화 관리 기능 배포](deploy-call-management-features.md)

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

