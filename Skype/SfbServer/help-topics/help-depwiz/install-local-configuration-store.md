---
title: 로컬 구성 저장소 설치
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 새 비즈니스용 Skype 서버 2015 역할 서버의 설치를 시작하려면 먼저 로컬 구성 저장소를 호스팅할 SQL Server 로컬 서버를 설치해야 합니다. 로컬 구성 저장소는 CMS(중앙 관리 저장소)의 읽기 전용 비즈니스용 Skype 서버 역할을 합니다. 컴퓨터의 로컬 관리자로 로컬 구성 저장소 설치 단계를 실행 중인 서버에 로그온하고 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원 자격을 가져야 합니다. 에지 서버에서 설치를 수행 중인 경우 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원일 필요가 없습니다. 토폴로지 작성기 정의 문서는 중앙 관리 저장소가 아닌 내보낼 정의 문서에서 읽습니다. 토폴로지 작성기 정의 문서를 내보내고 에지 서버에서 사용할 수 있도록 설정하는 경우 Export Your Topology and Copy It to External Media for Edge Installation 항목을 참조하십시오.
ms.openlocfilehash: e6634d90cba0c8ff07b6aa7a2c058e1dce467dc7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843141"
---
# <a name="install-local-configuration-store"></a>로컬 구성 저장소 설치

새 비즈니스용 Skype 서버 2015 역할 서버의 설치를 시작하려면 먼저 로컬 구성 저장소를 호스팅할 SQL Server 로컬 서버를 설치해야 합니다. 로컬 구성 저장소는 CMS(중앙 관리 저장소)의 읽기 전용 비즈니스용 Skype 서버 역할을 합니다. 컴퓨터의 로컬 관리자로 **로컬 구성 저장소 설치** 단계를 실행 중인 서버에 로그온하고 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원 자격을 가져야 합니다. 에지 서버에서 설치를 수행 중인 경우 RTCUniversalServerAdmins 또는 RTCUniversalGlobalReadOnlyGroup 그룹의 구성원일 필요가 없습니다. 토폴로지 작성기 정의 문서는 중앙 관리 저장소가 아닌 내보낼 정의 문서에서 읽습니다. 토폴로지 작성기 정의 문서를 내보내고 에지 서버에서 사용할 수 있도록 설정하는 경우 [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)항목을 참조하십시오.

설치를 시작하려면

1. 2015 비즈니스용 Skype 서버 **1단계:** 로컬 구성 저장소 설치 옆의 실행을 **클릭합니다.**

2. **로컬 서버 구성** 페이지에서 **중앙 관리 저장소의 구성 자동 검색** 옵션이 선택되어 있는지 확인하고 **다음** 을 클릭합니다.

3. 로컬 서버 구성 설치가 완료되면 **마침** 을 클릭합니다.

> [!NOTE]
> 로컬 로컬 설치 SQL Server 시간이 걸릴 수 있습니다. 설치하는 동안 설치 요약 화면에서 업데이트가 SQL Server 표시됩니다. 설치 진행률을 모니터링하려면 작업 관리자를 사용하여 설치 SQL Server 합니다.