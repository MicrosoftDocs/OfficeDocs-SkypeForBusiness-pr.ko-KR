---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 중앙 관리 저장소가 있는 내부 컴퓨터 또는 비즈니스용 Skype 서버 2019 핵심 구성 요소(OcsCore.msi)가 설치된 도메인에 가입된 컴퓨터에서 비즈니스용 Skype 서버 2019 Get-CsManagementStoreReplicationStatus cmdlet을 실행하여 에지 서버에 대한 구성 정보 복제의 유효성을 검사할 수 있습니다.
ms.openlocfilehash: e681781598af876f722094b0191aa784da2c533adc509a9f9fc4fad96fa4db4c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335748"
---
# <a name="verify-configuration-settings"></a>구성 설정 확인

중앙 관리 저장소가 있는 내부 컴퓨터 또는 비즈니스용 Skype 서버 2019 핵심 구성 요소(OcsCore.msi)가 설치된 도메인에 가입된 컴퓨터에서 비즈니스용 Skype 서버 2019 **Get-CsManagementStoreReplicationStatus** cmdlet을 실행하여 에지 서버에 대한 구성 정보 복제의 유효성을 검사할 수 있습니다. 
  
초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다.이 경우 **Invoke-CsManagementStoreReplication** cmdlet을 실행하여 복제가 완료될 때까지 기다린 후에 **Get-CsManagementStoreReplicationStatus** 를 다시 실행합니다. 
  

