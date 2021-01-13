---
title: 디렉터 풀 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: 디렉터 풀 FQDN 정의를 수행하려면 부하 분산 풀의 디렉터 두 개 이상으로 구성되는 다중 컴퓨터 풀 또는 단일 컴퓨터 풀을 선택합니다. 또한 Director 풀 또는 단일 감독의 FQDN에 연결하는 데 사용할 FQDN(FQDN)을 입력해야 합니다. 디렉터 컴퓨터 풀의 경우 이 값은 하드웨어 부하 분산 장치의 가상 IP에 대한 DNS(Domain Name System) 입력이나 DNS 부하 분산에 대한 공유 DNS 입력이 됩니다.
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807758"
---
# <a name="add-director-pool"></a>디렉터 풀 추가
 
**디렉터 풀 FQDN 정의** 를 수행하려면 부하 분산 풀의 디렉터 두 개 이상으로 구성되는 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀** 을 선택합니다. 또한 Director 풀 또는 단일 감독의 FQDN에 연결하는 데 사용할 FQDN(FQDN)을 입력해야 합니다. 디렉터 컴퓨터 풀의 경우 이 값은 하드웨어 부하 분산 장치의 가상 IP에 대한 DNS(Domain Name System) 입력이나 DNS 부하 분산에 대한 공유 DNS 입력이 됩니다.
  
> [!TIP]
> 나중에 디렉터 풀을 구현하려는 경우 **다중 컴퓨터 풀** 을 선택합니다. 풀이 부하 분산된 둘 이상의 컴퓨터로 정의되었더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터에 대한 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 더 추가할 준비가 된 경우 토폴로지 작성기를 다시 실행하여 새 풀 구성원을 정의하고 새 토폴로지 게시한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 Director 풀 구성원을 설정해야 합니다. 또한 적절한 풀용 부하 분산 장치, DNS(Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 새 풀 구성원을 추가해야 합니다. 대부분의 경우 두 부하 분산 시스템이 모두 설치되어 있습니다. 두 부하 분산 시스템 모두에 새 구성원 서버를 추가해야 합니다. 
  

