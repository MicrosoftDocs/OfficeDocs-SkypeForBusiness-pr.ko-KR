---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 중앙 관리 저장소가 있는 내부 컴퓨터에서 비즈니스용 Skype Server 2019 CsManagementStoreReplicationStatus cmdlet을 실행 하 여 Edge 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다. 비즈니스용 Skype 서버 2019 Core 구성 요소 (OcsCore)가 설치 되어 있는 도메인 가입 컴퓨터
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812756"
---
# <a name="verify-configuration-settings"></a>구성 설정 확인

중앙 관리 저장소가 있는 내부 컴퓨터에서 비즈니스용 Skype Server 2019 **CsManagementStoreReplicationStatus** cmdlet을 실행 하거나 비즈니스용 skype Server 2019 Core (ocscore)가 설치 되어 있는 도메인에 가입 된 컴퓨터에서 구성 정보 복제의 유효성을 검사할 수 있습니다. 
  
초기 결과에는 복제용으로 "True" 대신 상태가 "False"로 표시 될 수 있습니다. 이 경우 **CsManagementStoreReplication** cmdlet을 실행 하 고 **Get-CsManagementStoreReplicationStatus** 를 다시 실행 하기 전에 복제를 완료 하는 데 걸리는 시간을 허용 합니다. 
  

