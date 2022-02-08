---
title: 에지 컴퓨터 내부 IP 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: 이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.
ms.openlocfilehash: a35e9557e66c7a66312ab461a2c87d05940de12f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384996"
---
# <a name="add-edge-machine-internal-ip"></a>에지 컴퓨터 내부 IP 추가

이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.

지정하는 FQDN은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인에 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다. 컴퓨터 이름에 DNS 접미사를 추가하는 방법에 대한 자세한 내용은 [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)을 참조하십시오.