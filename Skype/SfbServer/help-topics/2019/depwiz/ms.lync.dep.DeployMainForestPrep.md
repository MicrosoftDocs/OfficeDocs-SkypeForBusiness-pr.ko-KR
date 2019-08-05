---
title: 현재 포리스트 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory 도메인 서비스 포리스트를 준비 하려면 스키마 준비 실행 항목에 설명 된 대로 스키마를 성공적으로 확장 하 고 스키마가 복제 되었는지 확인 해야 합니다.
ms.openlocfilehash: 810bfae1fd308ef943f41846a8baef774f4f724e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197421"
---
# <a name="prepare-current-forest"></a>현재 포리스트 준비

Active Directory 도메인 서비스 포리스트를 준비 하려면 스키마 [준비 실행](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)항목에 설명 된 대로 스키마를 성공적으로 확장 하 고 스키마가 복제 되었는지 확인 해야 합니다.

이러한 선행 조건을 완료한 후 **3단계: 현재 포리스트 준비**를 시작할 수 있습니다. 포리스트를 준비하려면 포리스트 루트에서 Domain Admins의 구성원으로 또는 준비할 포리스트에 대한 Enterprise Admins의 구성원으로 포리스트 루트에 있는 컴퓨터에 로그온합니다.

1. 배포 마법사의 **3단계: 현재 포리스트 준비**에서 **실행**을 클릭합니다.

2. **포리스트 준비** 페이지에서 **다음**을 클릭합니다.

    > [!NOTE]
    > 포리스트 준비를 사용 하 여 비즈니스용 Skype 서버용 유니버설 그룹을 배치할 위치를 선택할 수 있습니다. 조직의 요구 사항에 맞는 위치를 선택합니다.

3. **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다. 오류가 없는지 확인합니다. 경고를 검토하여 해당 경고가 인프라에 대해 예상된 것이며 일반적인 것인지 확인합니다.

4. 로그의 **작업** 열에서 **포리스트 Prep**을 확장 하 고 각 작업의 끝 ** \<에서\> 성공** 실행 결과를 찾아 포리스트 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 마침을 클릭 합니다. ** **.

5. 도메인 준비를 실행 하기 전에 Active Directory 도메인 서비스 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다. 모든 Active Directory 사이트의 도메인 컨트롤러 간 복제를 강제로 사이트 내에서 몇 분 내에 복제를 발생 시킵니다.

    > [!TIP]
    > 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 하는 Active Directory 도메인 서비스 사용자의 사용자 디렉터리에서 찾을 수 있습니다. 예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 위치 합니다.


