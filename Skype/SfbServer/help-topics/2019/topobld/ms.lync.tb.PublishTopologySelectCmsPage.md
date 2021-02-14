---
title: 토폴로지 게시 CMS 선택 페이지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 토폴로지 작성기에서 구성한 토폴로지가 게시됩니다. 중앙 관리 저장소를 보유하는 역할을 할 프런트 엔드 서버 또는 프런트 엔드 풀을 목록에서 선택해야 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀은 한 번만 이 역할을 보유할 수 있습니다.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822188"
---
# <a name="publish-topology-select-cms-page"></a>토폴로지 게시 CMS 선택 페이지
 
토폴로지 작성기에서 구성한 토폴로지가 게시됩니다. 중앙 관리 저장소를 보유하는 역할을 할 프런트 엔드 서버 또는 프런트 엔드 풀을 목록에서 선택해야 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀은 한 번만 이 역할을 보유할 수 있습니다. 
  
### <a name="about-the-central-management-server"></a>중앙 관리 서버
중앙 관리 서버는 데이터베이스의 읽기/쓰기 복사본이 중앙 관리 서버를 포함하는 프런트 엔드 서버에 의해 저장되는 단일 마스터/다중 복제본 시스템입니다. 중앙 관리 서버가 포함된 프런트 엔드 서버를 포함하여 토폴로지의 각 컴퓨터에는 설치 및 배포 중에 컴퓨터에 설치된 SQL Server 데이터베이스(기본적으로 RTCLOCAL)의 중앙 관리 저장소 데이터의 읽기 전용 복사본이 있습니다. 로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행되는 Lync Server Replica Replicator 에이전트를 통해 복제본 업데이트를 수신합니다. 중앙 관리 서버 및 로컬 복제 데이터베이스의 실제 데이터베이스 이름은 xds.mdf 및 xds.ldf 파일로 구성되는 XDS입니다. 마스터 데이터베이스 위치는 Active Directory 도메인 서비스의 SCP(서비스 제어 지점)에서 참조됩니다. 중앙 관리 서버를 사용하여 Lync Server를 관리 및 구성하는 모든 도구는 SCP를 사용하여 중앙 관리 저장소를 찾습니다.
  
## <a name="see-also"></a>참고 항목

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
