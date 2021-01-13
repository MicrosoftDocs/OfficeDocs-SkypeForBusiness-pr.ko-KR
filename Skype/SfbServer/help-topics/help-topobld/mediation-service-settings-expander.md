---
title: 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 중재 서버의 경우 다음을 지정할 수 있습니다.
ms.openlocfilehash: 0e6e9101b8b0a530b0f47411f1d8ce1eaa2e01b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810278"
---
# <a name="mediation-service-settings-expander"></a>중재 서비스 설정 확장기

**중재 서버** 에 대해 다음을 지정할 수 있습니다.

중재 서버를 프런트 엔드 풀 또는 Standard Edition 서버에 함께 사용하는 경우 중재 서버가 함께 사용 설정된 확인란을 **선택합니다.** 중재 서버를 배치하지 않도록 선택하면 이 섹션에서 정의할 수 있는 설정이 없습니다.

중재 서버 배치를 사용하도록 설정하면 TLS(전송 계층 보안)를 사용하도록 서버의 수신 대기 포트 범위를 정의해야 합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용** 을 선택하면 배치된 중재 서버의 TCP(Transmission Control Protocol) 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 공중 전화망(PSTN) 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.

배치된 중재 서버와 연결된 PSTN 게이트웨이를 정의합니다. 이미 게이트웨이를 정의한 경우 해당 게이트웨이를 중재 서버와 연결할 수 있습니다.

중재 서버와 연결된 게이트웨이가 둘 이상인 경우 연결된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다. 기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정** 을 클릭합니다. 기본값으로 설정한 게이트웨이의 선택을 취소하려면 **기본값으로 설정 안 함** 을 클릭합니다.

Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버의 설정을 정의 및 [](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) 구성하는 데 대한 자세한 내용은 토폴로지 정의 및 구성 및 중재 서버 배포 및 피어 정의를 [참조하세요.](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)


