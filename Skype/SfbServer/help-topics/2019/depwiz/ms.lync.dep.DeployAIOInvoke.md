---
title: 단일 Standard Edition 서버 준비(인보크)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: 명령 실행 페이지에서 SQL Server Express를 설치 하 고 중앙 관리 저장소로 작동 하도록 구성 하는 작업을 작업창에서 볼 수 있습니다. 기본적으로 RTC 라는 SQL Server 기반 데이터베이스의 인스턴스가 만들어집니다. 또한 서버 및 클라이언트에 대 한 인바운드 및 아웃 바운드 액세스를 허용 하 고 데이터베이스 및 인스턴스와 통신 하는 방화벽 규칙도 생성 됩니다. 작업이 완료 되 면 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일 이름은 부트스트랩 로컬 컴퓨터입니다. 로그 파일을 선택한 후 로그 보기를 클릭 합니다. 오류 및 경고가 있는지 로그 파일을 검토 합니다. 계속할 준비가 되 면 마침을 클릭 합니다. 이제 아직 토폴로지 작성기를 사용 하 여 토폴로지를 정의 해야 합니다.
ms.openlocfilehash: 900ef91184a13c67676cfd89a40694ce9fb6224a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705893"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>단일 Standard Edition 서버 준비(인보크)
 
**명령 실행** 페이지에서 SQL Server Express를 설치 하 고 중앙 관리 저장소로 작동 하도록 구성 하는 작업을 작업창에서 볼 수 있습니다. 기본적으로 RTC 라는 SQL Server 기반 데이터베이스의 인스턴스가 만들어집니다. 또한 서버 및 클라이언트에 대 한 인바운드 및 아웃 바운드 액세스를 허용 하 고 데이터베이스 및 인스턴스와 통신 하는 방화벽 규칙도 생성 됩니다. 작업이 완료 되 면 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일 이름은 **부트스트랩 로컬 컴퓨터**입니다. 로그 파일을 선택한 후 **로그 보기**를 클릭 합니다. 오류 및 경고가 있는지 로그 파일을 검토 합니다. 계속할 준비가 되 면 **마침을 클릭 합니다.** 이제 아직 토폴로지 작성기를 사용 하 여 토폴로지를 정의 해야 합니다.
  
> [!IMPORTANT]
> SQL Server Express 설치는 완료 하는 데 시간이 걸릴 수 있습니다. 설치 하는 동안 화면이 나 작업창에 진행률이 표시 되지 않습니다. 설치를 모니터링 하려면 Windows 작업 관리자를 사용 하 여 SQL Server 용 설치 파일 및 MSIExec 프로세스를 찾아야 합니다. 이 방법으로 설치 상태를 확인 하 고 설치가 진행 되 고 있는지 확인할 수 있습니다. 이 도움말 항목의 범위를 벗어나는 요인에 따라, SQL Server 인스턴스 설치를 완료 하는 데 최대 15 분 이상 걸릴 수 있습니다. 
  

