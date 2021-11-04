---
title: 에지 서버 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다. 에지 서버 또는 에지 서버 풀이 포함된 토폴로지 게시 및 비즈니스용 Skype 서버 배포하기 전에 외부 사용자 액세스 배포를 위한 모든 선행 비즈니스용 Skype 서버 완료해야 합니다. 이러한 필요 조건에 대한 자세한 내용은 배포 설명서의 Preparing for Installation of Servers in the Perimeter Network를 참조하십시오.
ms.openlocfilehash: 4436ce21de7402b53cd256224000457a06a2aa91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770546"
---
# <a name="add-edge-server"></a>에지 서버 추가

에지 서버 또는 에지 서버 풀을 토폴로지 디자인에 통합하려면 에지 서버 또는 에지 서버 풀을 배포할 서버의 FQDN(정규화된 도메인 이름)을 지정해야 합니다. 에지 서버 또는 에지 서버 풀이 포함된 토폴로지 게시 및 비즈니스용 Skype 서버 배포하기 전에 외부 사용자 액세스 배포를 위한 모든 선행 비즈니스용 Skype 서버 완료해야 합니다. 이러한 필수 구성 요소에 대한 자세한 내용은 배포 설명서에서 [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network)를 참조하십시오.

> [!IMPORTANT]
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인에 가입되지 않은 에지 서버 또는 에지 서버 풀로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다.

> [!TIP]
> 나중에 에지 서버 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다. 풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 더 추가할 준비가 되면 토폴로지 작성기에서 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 에지 서버 풀 구성원을 설정해야 합니다. 또한 적절한 풀용 부하 분산 장치, DNS 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다. 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다. 적절한 부하 분산 장치에 새 구성원 서버를 추가해야 합니다.

초기 토폴로지 배포 시 또는 초기 토폴로지를 배포한 후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버 또는 에지 서버 풀을 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.