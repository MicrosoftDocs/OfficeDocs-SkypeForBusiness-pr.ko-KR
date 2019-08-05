---
title: 디렉터 풀 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: 디렉터 풀 FQDN을 정의 하려면 부하 분산 된 풀 또는 단일 컴퓨터 풀에 두 개 이상의 디렉터로 구성 되는 다중 컴퓨터 풀을 선택 합니다. 또한 디렉터 풀 또는 단일 디렉터의 FQDN에 연결 하는 데 사용 되는 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다. 디렉터 컴퓨터 풀의 경우 하드웨어 로드 균형 조정기의 가상 IP에 대 한 DNS (도메인 이름 시스템) 항목이 나 DNS 부하 분산에 대 한 공유 DNS 항목이 될 수 있습니다.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197554"
---
# <a name="add-director-pool"></a>디렉터 풀 추가
 
**디렉터 풀 FQDN을 정의**하려면 부하 분산 된 풀 또는 **단일 컴퓨터 풀**에 두 개 이상의 디렉터로 구성 되는 **다중 컴퓨터 풀** 을 선택 합니다. 또한 디렉터 풀 또는 단일 디렉터의 FQDN에 연결 하는 데 사용 되는 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다. 디렉터 컴퓨터 풀의 경우 하드웨어 로드 균형 조정기의 가상 IP에 대 한 DNS (도메인 이름 시스템) 항목이 나 DNS 부하 분산에 대 한 공유 DNS 항목이 될 수 있습니다.
  
> [!TIP]
> 나중에 디렉터 풀을 구현 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다. 풀이 부하 분산 되는 두 대 이상의 컴퓨터로 정의 되어 있더라도 단일 컴퓨터 풀을 만들고 단일 컴퓨터용 풀 FQDN을 만들 수 있습니다. 나중에 풀에 컴퓨터를 추가할 준비가 되 면 토폴로지 작성기를 다시 실행 하 여 새 풀 구성원을 정의 하 고 새 토폴로지를 게시 한 다음 비즈니스용 Skype 서버 배포 마법사를 통해 새 디렉터 풀 구성원을 설정 해야 합니다. 또한 DNS (Domain Name System) 부하 분산 또는 하드웨어 부하 분산 장치에 대해 풀의 적절 한 부하 분산 장치에 새 풀 구성원을 추가 해야 합니다. 대부분의 경우에는 두 로드 균형 조정 시스템이 모두 준비 됩니다. 새 구성원 서버를 둘 다에 추가 하 고 있는지 확인 합니다. 
  

