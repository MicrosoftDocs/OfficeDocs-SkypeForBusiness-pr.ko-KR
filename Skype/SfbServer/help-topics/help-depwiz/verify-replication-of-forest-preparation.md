---
title: 포리스트 준비 복제 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 포리스트 준비 중에 글로벌 카탈로그의 복제 및 개체 만들기가 성공 했는지 확인 하려면 다음을 수행 합니다.
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700653"
---
# <a name="verify-replication-of-forest-preparation"></a>포리스트 준비 복제 확인
 
포리스트 준비 중에 글로벌 카탈로그의 복제 및 개체 만들기가 성공 했는지 확인 하려면 다음을 수행 합니다.
  
1. 도메인 컨트롤러 (다른 도메인 컨트롤러의 원격 사이트에 있는 경우)에서 포리스트 준비가 실행 되는 포리스트의 **Active Directory 사용자 및 컴퓨터**를 엽니다.
    
2. **Active Directory 사용자 및 컴퓨터**에서 포리스트 또는 자식 도메인의 도메인 이름을 확장 합니다.
    
3. 왼쪽 창에서 **사용자** 컨테이너를 클릭 하 고 오른쪽 창에서 유니버설 그룹 csadministrator를 찾습니다. CsAdministrator (Cs로 시작 하는 8 개의 새로운 유니버설 그룹)가 있는 경우 포리스트 준비의 복제에 성공 했습니다.
    
4. 그룹이 아직 표시 되지 않으면 복제를 강제로 수행 하거나 15 분 동안 기다렸다가 오른쪽 창을 새로 고칠 수 있습니다. 그룹이 있으면 복제가 완료 된 것입니다.
    
> [!TIP]
> 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 하려는 경우 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 하는 Active Directory 도메인 서비스 사용자의 사용자 디렉터리에서 찾을 수 있습니다. 예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 위치 합니다. 
  

