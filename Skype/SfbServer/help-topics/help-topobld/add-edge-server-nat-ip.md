---
title: Edge Server NAT IP 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 공용 IP 주소는 NAT (network address translation)에서 사용 되는 IP 주소입니다. IP 주소를 공개적으로 라우팅할 수 있어야 합니다. 이 마법사의 기능 선택 페이지에서이 Edge 풀의 외부 IP 주소를 NAT 옵션으로 번역 하도록 선택 했기 때문에이 요구 사항입니다.
ms.openlocfilehash: 55200991a0674c6372de9f44c2511e700166bebf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196433"
---
# <a name="add-edge-server-nat-ip"></a>Edge Server NAT IP 추가

공용 IP 주소는 NAT (network address translation)에서 사용 되는 IP 주소입니다. IP 주소를 공개적으로 라우팅할 수 있어야 합니다. 이 마법사의 **기능 선택** 페이지에서 **이 Edge 풀의 외부 IP 주소를 NAT 옵션으로 번역** 하도록 선택 했기 때문에이 요구 사항입니다.

> [!NOTE]
> NAT (Network address translation)를 사용 하 여 개인 네트워크 (예: 192.168.0.0 range)의 클라이언트나 서버가 공용 인터넷 네트워크를 통해 원격 네트워크의 시스템과 통신할 수 있습니다. NAT는 외부 인터페이스에서 단일 공용 IP 주소를 사용 하 고 내부 IP 주소를 하나의 공용 IP 주소와 연결 하 여 작동 합니다. NAT 매핑은 내부 주소를 외부 공용 IP 주소에 매핑합니다. 원격 시스템은 원본의 공용 주소만 볼 수 있습니다. 원격 시스템은 원본에 응답 하 고, 원본은 NAT 맵을 참조 하 여 응답을 반환 해야 하는 내부 IP 주소를 결정 합니다.

초기 토폴로지를 배포할 때 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하세요.


