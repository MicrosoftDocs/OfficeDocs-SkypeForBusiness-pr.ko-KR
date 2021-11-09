---
title: 단일 Standard Edition Server 준비(호출)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 명령 실행 페이지에서 SQL Server Express 설치하고 중앙 관리 저장소 역할을 하도록 구성하는 작업을 작업 창에서 볼 수 있습니다. 기본적으로 RTC라는 SQL Server 데이터베이스의 인스턴스가 만들어집니다. 서버 및 클라이언트가 데이터베이스 및 인스턴스와 통신할 수 있도록 인바운드 및 아웃바운드 액세스를 허용하기 위한 방화벽 규칙도 만들어집니다. 작업이 완료된 후 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일의 이름은 부트스트랩 로컬 컴퓨터입니다. 로그 파일을 선택한 후 로그 보기를 클릭합니다. 로그 파일을 검토하여 오류 및 경고가 있는 지 확인합니다. 계속할 준비가 되면 마침을 클릭합니다. 아직 수행하지 않은 경우 토폴로지 작성기에서 토폴로지 정의를 완료해야 합니다.
ms.openlocfilehash: 8d72d69b8c5ea676bf1e944bda143ad8f56fea82
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841590"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>단일 Standard Edition Server 준비(호출)
 
명령  실행 페이지에서 SQL Server Express 설치하고 중앙 관리 저장소 역할을 하도록 구성하는 작업을 작업 창에서 볼 수 있습니다. 기본적으로 RTC라는 SQL Server 데이터베이스의 인스턴스가 만들어집니다. 서버 및 클라이언트가 데이터베이스 및 인스턴스와 통신할 수 있도록 인바운드 및 아웃바운드 액세스를 허용하기 위한 방화벽 규칙도 만들어집니다. 작업이 완료된 후 드롭다운 목록에서 로그 파일을 선택할 수 있습니다. 로그 파일의 이름은 **부트스트랩 로컬 컴퓨터** 입니다. 로그 파일을 선택한 후 **로그 보기** 를 클릭합니다. 로그 파일을 검토하여 오류 및 경고가 있는 지 확인합니다. 계속할 준비가 되면 **마침** 을 클릭합니다. 아직 수행하지 않은 경우 토폴로지 작성기에서 토폴로지 정의를 완료해야 합니다.
  
> [!IMPORTANT]
> 설치를 SQL Server Express 시간이 걸릴 수 있습니다. 설치하는 동안 화면이나 작업 창에 진행률이 표시되지 않습니다. 설치를 모니터링하려면 작업 관리자를 사용하여 Windows MSIExec 프로세스 및 설치 파일을 찾아야 SQL Server. 이 방법으로 설치 상태를 보고 설치가 진행 중인지를 확인할 수 있습니다. 이 도움말 항목의 범위를 벗어났던 요소에 따라 설치를 완료하는 데 최대 15분 SQL Server 수 있습니다. 
  

