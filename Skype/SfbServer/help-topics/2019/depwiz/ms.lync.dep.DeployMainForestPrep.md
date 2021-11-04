---
title: 현재 포리스트 준비
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory 도메인 서비스 포리스트를 준비하려면 Running Schema Preparation 항목에 설명된 바와 같이 성공적으로 해당 스마마를 확장하고 해당 스마가 복제되어 있는지 확인합니다.
ms.openlocfilehash: 65cb63a2ac2ea9273ed27f31fd679efe6e00ba3a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738674"
---
# <a name="prepare-current-forest"></a>현재 포리스트 준비

Active Directory 도메인 서비스 포리스트를 준비하려면 [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)항목에 설명된 바와 같이 성공적으로 확장해야 합니다.

이러한 선행 조건을 완료한 후 **3단계: 현재 포리스트 준비** 를 시작할 수 있습니다. 포리스트를 준비하려면 포리스트 루트에서 Domain Admins의 구성원으로 또는 준비할 포리스트에 대한 Enterprise Admins의 구성원으로 포리스트 루트에 있는 컴퓨터에 로그온합니다.

1. 배포 마법사의 **3단계: 현재 포리스트 준비** 에서 **실행** 을 클릭합니다.

2. **포리스트 준비** 페이지에서 **다음** 을 클릭합니다.

    > [!NOTE]
    > 포리스트 준비를 사용하면 포리스트에 대한 유니버설 그룹을 두는 위치를 선택할 수 비즈니스용 Skype 서버. 조직의 요구 사항에 맞는 위치를 선택합니다.

3. **명령 실행** 페이지에서 **작업 상태: 완료됨** 을 찾은 다음 **로그 보기** 를 클릭합니다. 오류가 없는지 확인합니다. 경고를 검토하여 해당 경고가 인프라에 대해 예상된 것이며 일반적인 것인지 확인합니다.

4. 로그의 **작업** 열에서 **포리스트** 준비를 확장하고 각 작업 끝에 있는 실행 결과를 찾아 포리스트 준비가 성공적으로 완료된지 확인하고 로그를 닫고 마친 을 **\<Success\>** **클릭합니다.**

5. 도메인 준비를 실행하기 전에 포리스트 루트 도메인 컨트롤러의 **Active Directory 사이트** 및 서비스 스냅인에 나열된 모든 도메인 컨트롤러로 Active Directory 도메인 서비스 복제가 완료될 때까지 기다리거나 복제를 강제로 실행합니다. 몇 분 내에 사이트 내부에서 복제가 발생하도록 모든 Active Directory 사이트의 도메인 컨트롤러 간에 복제를 적용합니다.

    > [!TIP]
    > 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터의 해당 단계를 실행한 Active Directory 도메인 서비스 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다. 예를 들어 사용자가 도메인 관리자로 로그인한 Contoso.net 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.