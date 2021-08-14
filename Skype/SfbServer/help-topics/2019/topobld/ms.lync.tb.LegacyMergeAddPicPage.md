---
title: 레거시 병합
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: 웹 회의 외부 FQDN은 외부 사용자가 온-프레미스 모임에 참가할 수 있도록 허용합니다. 레거시 에지 서버의 웹 회의 외부 인터페이스 FQDN(정규화된 도메인 이름)을 입력합니다.
ms.openlocfilehash: 586a9022602de97526b262b612d3e87e0a174ccc12a728b57d0664d9d05317b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342343"
---
# <a name="legacy-merge"></a>레거시 병합

**웹 회의 외부 FQDN** 은 외부 사용자가 온-프레미스 모임에 참가할 수 있도록 허용합니다. 레거시 에지 서버의 웹 회의 외부 인터페이스 FQDN(정규화된 도메인 이름)을 입력합니다.

**외부 웹 회의 외부 포트** 값 **443** 은 회의 클라이언트에 대해 구성된 기본 TCP(Transmission Control Protocol) SIP(Session Initiation Protocol) 포트입니다. 기본값이 사용되지 않으면 **외부 웹 회의 외부 포트** 값을 업데이트합니다.

이 에지 서버를 페더레이션에 사용하려면 **이 에지 풀은 페더레이션 및 공용 IM 연결에 사용됩니다** 확인란을 선택합니다. 에지 서버가 여러 대 배포되어 있으면 이 중 한 대만 페더레이션에 사용하도록 설정됩니다. 이 확인란을 선택하지 않고 나중에 페더레이션을 사용하도록 설정하려는 경우 토폴로지를 게시하고 토폴로지 작성기 병합 마법사를 다시 실행해야 합니다. 자세한 내용은 [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)을 참조하십시오.