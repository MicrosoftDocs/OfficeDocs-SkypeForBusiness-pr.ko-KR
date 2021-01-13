---
title: 레거시 병합 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: 액세스 에지 풀 내부 FQDN은 내부 사용자가 페더전, 원격 사용자 액세스 및 공용 IM 연결을 위해 외부 사용자와 통신하는 다양한 시나리오에 사용됩니다. 레거시 환경에 부하 분산 에지 서버가 배포된 경우 내부 부하 분산 장치의 FQDN(정규화된 도메인 이름)을 입력합니다.
ms.openlocfilehash: 9e4446a89b1f8976db4d325175c3e760865ac118
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827448"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="6ba59-104">레거시 병합 FQDN</span><span class="sxs-lookup"><span data-stu-id="6ba59-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="6ba59-p102">**에지 풀 내부 FQDN 액세스** 는 내부 사용자가 페더레이션, 원격 사용자 액세스 및 공용 IM 연결을 위해 외부 사용자와 통신하는 다양한 시나리오에서 사용됩니다. 레거시 환경에 부하 분산 에지 서버가 배포된 경우 내부 부하 분산 장치의 FQDN(정규화된 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba59-p102">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity. If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="6ba59-p103">**내부 SIP 액세스 포트** 값 **5061** 은 클라이언트, 레거시 프런트 엔드 풀 및 서버와의 통신에 사용되는 기본 TCP(Transmission Control Protocol) SIP 포트입니다. 기본값을 사용하지 않는 경우 **내부 SIP 액세스 포트:** 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba59-p103">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers. If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

