---
title: 로컬 구성 저장소 호출 (구성) 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 중앙 관리 저장소의 로컬 읽기 전용 복사본을 보유 하 고 있는 데이터베이스 설치를 시작 하려면 이미 설치 및 구성 된 중앙의 토폴로지 작성기를 사용 하 여 게시 된 정의 된 구성을 검색 하도록 선택 합니다. 관리 저장소에 저장 하거나 다른 미디어에서 정의 된 구성을 읽습니다. 조직의 내부 네트워크에 있는 컴퓨터의 경우 중앙 관리 저장소에서 자동으로 구성 검색을 선택 합니다.
ms.openlocfilehash: b4249f4968c51fb901e612b2414bb2c6921be40c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197406"
---
# <a name="install-local-configuration-store-invoke-configure"></a>로컬 구성 저장소 호출 (구성) 설치
 
중앙 관리 저장소의 로컬 읽기 전용 복사본을 보유 하 고 있는 데이터베이스 설치를 시작 하려면 이미 설치 및 구성 된 중앙의 토폴로지 작성기를 사용 하 여 게시 된 정의 된 구성을 검색 하도록 선택 합니다. 관리 저장소에 저장 하거나 다른 미디어에서 정의 된 구성을 읽습니다. 조직의 내부 네트워크에 있는 컴퓨터의 경우 **중앙 관리 저장소에서 자동으로 구성 검색**을 선택 합니다.
  
Edge 서버에 중앙 관리 저장소의 복제본을 설치 하는 경우 USB 플래시 드라이브, USB 하드 디스크 드라이브, CD-ROM 또는 기타 미디어와 같은 휴대용 미디어에서 구성 문서의 내보낸 복사본을 읽도록 선택 합니다. 
  
> [!IMPORTANT]
> Edge 서버에 로컬 구성 저장소를 설치 하는 경우 Windows PowerShell cmdlet을 실행 하 여 중앙 관리 저장소에서 내보낸 형식으로 구성 정보를 가져와야 합니다.`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
적절 한 옵션을 선택한 후 **다음**을 클릭 합니다.
  

