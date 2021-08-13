---
title: 포리스트 준비 복제 확인
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 포리스트 준비 중 개체 만들기 및 전역 카탈로그 복제가 정상적으로 수행되었는지 확인하려면 다음을 수행합니다.
ms.openlocfilehash: 08447b011ba16aadbda39b2ff89edc47db56c714d6933d5467757e2c45abde7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317833"
---
# <a name="verify-replication-of-forest-preparation"></a>포리스트 준비 복제 확인
 
포리스트 준비 중 개체 만들기 및 전역 카탈로그 복제가 정상적으로 수행되었는지 확인하려면 다음을 수행합니다.
  
1. 포리스트 준비가 실행된 포리스트의 도메인 컨트롤러(가급적이면 다른 도메인 컨트롤러의 원격 사이트)에서 **Active Directory 사용자 및 컴퓨터** 를 엽니다.
    
2. **Active Directory 사용자 및 컴퓨터** 에서 포리스트 또는 자식 도메인의 도메인 이름을 확장합니다.
    
3. 왼쪽 창에서 **사용자** 컨테이너를 클릭하고 오른쪽 창에서 유니버설 그룹 CsAdministrator를 검색합니다. Cs로 시작하는 다른 8개의 새 유니버설 그룹 중 CsAdministrator가 있는 경우 포리스트 준비 복제가 성공한 것입니다.
    
4. 그룹이 아직 없으면 복제를 적용하거나 15분간 기다린 후 오른쪽 창을 새로 고칠 수 있습니다. 그룹이 나타나면 복제가 완료된 것입니다.
    
> [!TIP]
> 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토하려면 배포 마법사를 실행한 컴퓨터에서 해당 단계를 실행한 Active Directory 도메인 서비스 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다. 예를 들어 사용자가 도메인 관리자로 로그인한 Contoso.net 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다. 
  

