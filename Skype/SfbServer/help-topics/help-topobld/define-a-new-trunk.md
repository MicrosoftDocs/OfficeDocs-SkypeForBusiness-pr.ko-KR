---
title: 새 트렁크 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 다음 정보를 제공 하 여 새 SIP (session 착수 프로토콜) 트렁크를 정의 합니다.
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218559"
---
# <a name="define-a-new-trunk"></a>새 트렁크 정의

다음 정보를 제공 하 여 새 SIP (session 착수 프로토콜) 트렁크를 정의 합니다.

- **트렁크 이름**: 토폴로지에서이 트렁크를 식별할 고유한 이름입니다.

- **연결 된 Pstn 게이트웨이**: 배포에 있는 배포 및 구성 된 pstn 게이트웨이를 목록에서 선택 합니다.

- Ip **/pstn 게이트웨이의 수신 대기 포트**: IP-PBX 또는 pstn 게이트웨이가 수신 대기 하는 포트입니다. 배포에 구성 된 다른 모든 트렁크 수신 대기 포트에서 고유 해야 합니다.

- **SIP 전송 프로토콜**: 목록에서 TCP 또는 TLS 중 하나를 선택 합니다.

- **연결 된 중재 서버**: 배포에 배포 되 고 구성 된 중재 서버를 목록에서 선택 합니다.

- **연결 된 중재 서버 포트**:이 SIP 트렁크에서 사용할 중재 서버의 TCP 또는 TLS 포트 값과 동일 하 게 포트 값을 설정 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 M:N 트렁크](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP 트렁크를 구현 하려면 어떻게 해야 하나요?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
