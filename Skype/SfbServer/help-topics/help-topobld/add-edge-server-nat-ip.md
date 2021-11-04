---
title: 에지 서버 NAT IP 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 공용 IP 주소는 NAT(Network Address Translation)에서 사용되는 IP 주소입니다. IP 주소는 공개적으로 라우팅 가능해야 합니다. 이러한 이유는 이 마법사의 기능 선택 페이지에서 이 에지 풀의 외부 IP 주소가 NAT에 의해 변환됩니다 옵션을 선택했기 때문입니다.
ms.openlocfilehash: 6aa2a3444158e32f62288dc9c572aad8c067f8ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776358"
---
# <a name="add-edge-server-nat-ip"></a>에지 서버 NAT IP 추가

공용 IP 주소는 NAT(Network Address Translation)에서 사용되는 IP 주소입니다. IP 주소는 공개적으로 라우팅 가능해야 합니다. 이러한 이유는 이 마법사의 **기능 선택** 페이지에서 **이 에지 풀의 외부 IP 주소가 NAT에 의해 변환됩니다** 옵션을 선택했기 때문입니다.

> [!NOTE]
> NAT(Network Address Translation)는 사설망(예: 192.168.0.0 범위)에 있는 클라이언트 또는 서버가 공용 인터넷 네트워크를 통해 원격 네트워크에 있는 시스템과 통신할 수 있도록 합니다. NAT는 외부 인터페이스에서 단일 공용 IP 주소를 사용하고 내부 IP 주소를 단일 공용 IP 주소와 연결하여 작동합니다. NAT 매핑은 내부 주소를 외부 공용 IP 주소에 매핑합니다. 원격 시스템에는 원본의 공용 주소만 표시됩니다. 원격 시스템은 원본에 응답하고 원본은 NAT 맵을 참조하여 응답을 반환해야 할 내부 IP 주소를 확인합니다.

초기 토폴로지를 배포할 때 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.