---
title: 프런트 엔드 풀 FQDN 추가
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
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 만들 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)을 지정합니다. 프런트 엔드 풀이 포함된 토폴로지를 게시한 후에는 풀의 FQDN을 변경할 수 없습니다. 풀의 이름을 바꿔야 할 경우 풀을 삭제한 다음 새 FQDN으로 새 풀을 추가해야 합니다.
ms.openlocfilehash: 7f58f0fb410cff185900138a7ea5c112c359c38f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862595"
---
# <a name="add-front-end-pool-fqdn"></a>프런트 엔드 풀 FQDN 추가
 
만들 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)을 지정합니다. 프런트 엔드 풀이 포함된 토폴로지를 게시한 후에는 풀의 FQDN을 변경할 수 없습니다. 풀의 이름을 바꿔야 할 경우 풀을 삭제한 다음 새 FQDN으로 새 풀을 추가해야 합니다.
  
> [!TIP]
> 나중에 프런트 엔드 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다. 풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 더 추가할 준비가 되면 토폴로지 작성기 를 다시 실행하여 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 프런트 엔드 풀 구성원을 설정해야 합니다. 또한 적절한 풀용 부하 분산 장치, DNS(Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다. 대부분의 경우 두 부하 분산 시스템이 모두 설치되어 있습니다. 두 부하 분산 시스템 모두에 새 구성원 서버를 추가해야 합니다. 
  

