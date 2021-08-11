---
title: 프런트 엔드 연결 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 지금 서버 역할과 프런트 엔드 풀을 연결하여 다른 서버 배포가 필요한 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.
ms.openlocfilehash: 3564457b392e2c122577fb421f5511beb9febd7fbff5ac15bdaec2803263b043
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285298"
---
# <a name="add-front-end-associations"></a>프런트 엔드 연결 추가

지금 서버 역할과 프런트 엔드 풀을 연결하여 다른 서버 배포가 필요한 특정 기능에 대한 지원을 사용하도록 설정할 수 있습니다. 또한 나중에 서버 역할과 프런트 엔드 풀을 연결할 수 있습니다. 프런트 엔드 풀과 연결할 수 있는 서버 역할은 다음과 같습니다.

- A/V 에지 서버. A/V 에지 서버 구현에 대한 자세한 내용은 계획 설명서에서 [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)을 참조하십시오.

> [!IMPORTANT]
> 지금 이러한 기능 중 원하는 기능에 대한 지원을 사용하도록 설정하는 경우 게시하는 토폴로지 디자인에 선택한 각 기능의 구현에 필요한 서버 구성 요소가 포함됩니다. 토폴로지를 오류 없이 성공적으로 게시하려면 물리적 컴퓨터를 도메인에 가입시켜야 합니다. 예를 들어 지금 보관에 대한 지원을 사용하도록 설정하는 경우 조직의 통신 보관을 시작하기 전에 보관 서버를 배포하고 적절한 보관 옵션을 구성해야 합니다.