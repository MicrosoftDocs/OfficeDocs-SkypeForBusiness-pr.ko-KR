---
title: 현재 도메인 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: '비즈니스용 Skype Server 또는 비즈니스용 Skype Server 사용자를 실행 하는 서버를 호스트 하기 위해 도메인을 준비 하려면 설치 프로그램을 사용 하 여 도메인 준비를 실행 하는 항목에 설명 된 대로 5 단계: 현재 도메인 준비를 완료 해야 합니다. 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.'
ms.openlocfilehash: 16b47a211ebff577844cdc29b6e28acd00952d20
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197422"
---
# <a name="prepare-current-domain"></a>현재 도메인 준비

비즈니스용 Skype Server 또는 비즈니스용 Skype Server 사용자를 실행 하는 서버를 호스트 하기 위해 도메인을 준비 하려면 [설치 프로그램을 사용 하 여 도메인 준비를 실행 하](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)는 항목에 설명 된 대로 **5 단계: 현재 도메인 준비**를 완료 해야 합니다. 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.

1. 비즈니스용 Skype Server 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 비즈니스용 Skype 서버 배포 마법사를 시작 합니다.

2. **Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.

3. **5단계: 현재 도메인 준비**에서 **실행**을 클릭합니다.

4. **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

5. **작업** 열에서 **도메인 Prep**을 확장 하 고 각 작업의 끝에서 ** \<성공\> ** 실행 결과를 찾아 도메인 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.

> [!TIP]
> 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 해야 하는 경우에는 해당 단계를 실행 하는 Active Directory 도메인 서비스 사용자의 사용자 디렉터리에서 배포 마법사가 실행 된 컴퓨터에서 찾을 수 있습니다. 예를 들어 사용자가 도메인 Contoso.net의 도메인 관리자로 로그인 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp.에 위치 합니다.


