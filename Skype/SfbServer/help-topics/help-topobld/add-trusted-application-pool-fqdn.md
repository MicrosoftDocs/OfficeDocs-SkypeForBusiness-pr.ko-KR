---
title: 신뢰할 수 있는 응용 프로그램 풀 FQDN 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 신뢰할 수 있는 응용 프로그램 풀 FQDN(정규화된 도메인 이름)을 정의하려면 다음을 지정합니다.
ms.openlocfilehash: 9ad9797dd49af2c5a267bb8e0c581b3a5bcb97ec
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844431"
---
# <a name="add-trusted-application-pool-fqdn"></a>신뢰할 수 있는 응용 프로그램 풀 FQDN 추가
 
신뢰할 수 있는 응용 프로그램 풀 FQDN(정규화된 도메인 이름)을 정의하려면 다음을 지정합니다.
  
신뢰할 수 있는 응용 프로그램을 호스팅할 서버 또는 서버 풀의 FQDN
  
부하 분산 및 고가용성의 신뢰할 수 있는 응용 프로그램에 대한 서버 풀을 배포하는 경우 **다중 컴퓨터 풀** 을 선택하고 부하 분산이나 고가용성이 필요하지 않은 경우 **단일 컴퓨터 풀** 을 선택합니다.
  
> [!IMPORTANT]
> 단일 신뢰할 수 있는 응용 프로그램 서버를 나중에 서버 풀로 변환할 수는 없습니다. 나중에 풀이 필요할 수도 있다고 생각되는 경우 지금 단일 컴퓨터가 포함된 다중 서버 풀을 배포하고 필요할 때 서버를 추가할 수 있습니다. 
  
신뢰할 수 있는 응용 프로그램 풀에 대한 자세한 내용은 [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)을 참조하십시오.
