---
title: 에지 서버 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다. 에 지 서버 또는에 지 서버 풀을 포함 하 고 비즈니스용 Skype 서버를 설치 하는 토폴로지를 게시 하기 전에 외부 사용자 액세스를 배포 하기 위한 모든 필수 구성 요소를 완료 해야 합니다. 이러한 필요 조건에 대한 자세한 내용은 배포 설명서의 Preparing for Installation of Servers in the Perimeter Network를 참조하십시오.
ms.openlocfilehash: 379c181336ecc855feb1344e3328a8ffcd38f447
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216749"
---
# <a name="add-edge-server"></a>에지 서버 추가

에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다. 에 지 서버 또는에 지 서버 풀을 포함 하 고 비즈니스용 Skype 서버를 설치 하는 토폴로지를 게시 하기 전에 외부 사용자 액세스를 배포 하기 위한 모든 필수 구성 요소를 완료 해야 합니다. 이러한 필수 구성 요소에 대한 자세한 내용은 배포 설명서에서 [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)를 참조하십시오.

> [!IMPORTANT]
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인에 가입되지 않은 에지 서버 또는 에지 서버 풀로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다.

> [!TIP]
> 나중에 에지 서버 풀을 구현하려는 경우 **다중 컴퓨터 풀**을 선택합니다. 풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 더 추가할 준비가 되 면 토폴로지 작성기를 다시 수행 하 여 새 풀 구성원을 정의 하 고, 새 토폴로지를 게시 한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새에 지 서버 풀 구성원을 설정 해야 합니다. 또한 적절한 풀용 부하 분산 장치, DNS 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다. 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다. 적절한 부하 분산 장치에 새 구성원 서버를 추가해야 합니다.

초기 토폴로지 배포 시 또는 초기 토폴로지를 배포한 후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버 또는 에지 서버 풀을 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.


