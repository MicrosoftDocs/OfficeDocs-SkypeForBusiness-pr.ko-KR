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
description: 중앙 관리 저장소가 있는 내부 컴퓨터 또는 비즈니스용 Skype 서버 2019 코어 구성 요소 (OcsCore.msi)가 설치 된 도메인에 가입 된 컴퓨터에서 비즈니스용 Skype 서버 2019-Get-csmanagementstorereplicationstatus cmdlet을 실행 하 여에 지 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다.
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752150"
---
# <a name="verify-configuration-settings"></a>구성 설정 확인

중앙 관리 저장소가 있는 내부 컴퓨터에서 비즈니스용 Skype 서버 2019 **get-csmanagementstorereplicationstatus** cmdlet을 실행 하거나, 비즈니스용 skype 서버 2019 Core 구성 요소 (OcsCore.msi)가 설치 되어 있는 도메인에 가입 된 컴퓨터에서 해당 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다. 
  
초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다. 이 경우 **Invoke-CsManagementStoreReplication** cmdlet을 실행하고 복제가 완료될 때까지 기다린 후에 **Get-CsManagementStoreReplicationStatus**를 다시 실행합니다. 
  

