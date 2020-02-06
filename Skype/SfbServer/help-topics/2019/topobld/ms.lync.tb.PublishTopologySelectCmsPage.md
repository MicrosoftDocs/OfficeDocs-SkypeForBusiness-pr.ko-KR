---
title: 토폴로지 게시 CMS 페이지 선택
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 토폴로지 작성기를 사용 하 여 구성한 토폴로지를 게시 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀이 중앙 관리 저장소 보관 역할을 맡을 목록에서 선택 하 라는 메시지가 표시 됩니다. 지정 된 시간에이 역할을 보유할 수 있는 프런트 엔드 서버 또는 프런트 엔드 풀은 하나만 있습니다.
ms.openlocfilehash: cae0f79b9787458ae1dd24077dfdd46689378414
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795419"
---
# <a name="publish-topology-select-cms-page"></a>토폴로지 게시 CMS 페이지 선택
 
토폴로지 작성기를 사용 하 여 구성한 토폴로지를 게시 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀이 중앙 관리 저장소 보관 역할을 맡을 목록에서 선택 하 라는 메시지가 표시 됩니다. 지정 된 시간에이 역할을 보유할 수 있는 프런트 엔드 서버 또는 프런트 엔드 풀은 하나만 있습니다. 
  
### <a name="about-the-central-management-server"></a>중앙 관리 서버 정보
중앙 관리 서버는 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있는 단일 마스터/다중 복제 시스템입니다. 중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 하는 동안 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 이라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 있습니다. 배포가. 로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제본 업데이트를 받습니다. 중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds, xds .mdf 파일로 구성 되는 XDS입니다. Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다. 중앙 관리 서버를 사용 하 여 Lync Server를 관리 하 고 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.
  
## <a name="see-also"></a>참고 항목

[이동-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
