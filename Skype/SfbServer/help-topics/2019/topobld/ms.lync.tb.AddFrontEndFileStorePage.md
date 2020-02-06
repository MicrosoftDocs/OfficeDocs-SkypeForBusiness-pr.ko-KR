---
title: 프런트 엔드 파일 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: fa64037cbcd4347a416832d46c88e2b2105c1aeb
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798555"
---
# <a name="add-front-end-file-store"></a>프런트 엔드 파일 저장소 추가

Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> 파일 공유는 Enterprise Edition 프런트 엔드 서버에는 배치할 수 없지만 Standard Edition 서버에는 배치할 수 있습니다.

> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의한, 정의된 위치에 파일 공유를 만들어야 합니다.

> [!IMPORTANT]
> 토폴로지에 Enterprise 프런트 엔드 풀 또는 Standard Edition 서버를 추가할 때 토폴로지 작성기에서 파일 저장소를 설정하여 파일 저장소로 사용할 파일 공유에 대한 DACL(임의 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유의 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)를 참조하세요. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서에서 [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하세요. Enterprise Edition 프런트 엔드 풀용 토폴로지를 디자인하는 방법에 대한 자세한 내용은 배포 설명서에서 [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)을 참조하세요.


