---
title: 디렉터 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 56fb33653f2f463e9b336ae447a1c665680ed6df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100144"
---
# <a name="add-director-file-store"></a>디렉터 파일 저장소 추가

디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> 토폴로지에 디렉터를 추가하면 토폴로지를 게시할 때 파일 저장소를 설정하고 파일 저장소로 사용할 파일 공유에 대한 DACL(임의 액세스 제어 목록)을 구성하기 위한 적절한 권한이 필요합니다. 이렇게 하려면 토폴로지 작성기를 실행하고 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유의 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 File [Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 및 배포 [설명서의 SQL Server Data and Log File Placement를](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 참조하십시오. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)를 참조하십시오. 디렉터용 토폴로지를 디자인하는 방법에 대한 자세한 내용은 배포 설명서에서 [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology)를 참조하십시오.