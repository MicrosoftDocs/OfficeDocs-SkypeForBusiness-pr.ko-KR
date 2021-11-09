---
title: 로컬 구성 저장소 설치 호출(구성)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 중앙 관리 저장소의 로컬 읽기 전용 복사본을 보유할 데이터베이스의 설치를 시작하려면 이미 설치 및 구성된 중앙 관리 저장소에서 토폴로지 작성기에서 게시된 정의된 구성을 검색하거나 다른 미디어에서 정의된 구성을 읽는 방법을 선택합니다. 조직의 내부 네트워크에 있는 컴퓨터의 경우 중앙 관리 저장소에서 자동으로 구성 검색을 선택합니다.
ms.openlocfilehash: 86bc9d9851a064583ad5c318c6665b63bfdbf09b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852442"
---
# <a name="install-local-configuration-store-invoke-configure"></a>로컬 구성 저장소 설치 호출(구성)
 
중앙 관리 저장소의 로컬 읽기 전용 복사본을 보유할 데이터베이스의 설치를 시작하려면 이미 설치 및 구성된 중앙 관리 저장소에서 토폴로지 작성기에서 게시된 정의된 구성을 검색하거나 다른 미디어에서 정의된 구성을 읽는 방법을 선택합니다. 조직의 내부 네트워크에 있는 컴퓨터의 경우 중앙 관리 저장소에서 자동으로 구성 **검색을 선택합니다.**
  
에지 서버에 중앙 관리 저장소의 복제본을 설치하는 경우 USB 플래시 드라이브, USB 하드 디스크 드라이브, CD-ROM 또는 기타 미디어와 같은 휴대용 미디어에서 내보낸 구성 문서의 복사본을 읽도록 선택합니다. 
  
> [!IMPORTANT]
> 에지 서버에 로컬 구성 저장소를 설치하는 경우 구성 정보는 다음 cmdlet을 실행하여 중앙 관리 저장소에서 내보낼 Windows PowerShell 합니다.`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
적절한 옵션을 선택한 후 **다음** 을 클릭합니다.
  

