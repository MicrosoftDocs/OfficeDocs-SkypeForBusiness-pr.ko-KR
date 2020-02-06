---
title: 보관 서버 파일 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: IM(메신저 대화) 및 웹 회의(모임) 콘텐츠를 둘 다 보관하도록 하려면 모든 웹 회의 콘텐츠의 복사본용 파일 저장소로 사용할 파일 저장소를 지정해야 합니다. 기존 파일 공유를 보관 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 4d8f14ec4cd4e63f7c1c48beb57cc2edbf6a56b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821300"
---
# <a name="add-archiving-server-file-store"></a>보관 서버 파일 저장소 추가

IM(메신저 대화) 및 웹 회의(모임) 콘텐츠를 둘 다 보관하도록 하려면 모든 웹 회의 콘텐츠의 복사본용 파일 저장소로 사용할 파일 저장소를 지정해야 합니다. 기존 파일 공유를 보관 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의된 위치에 파일 공유를 만들어야 합니다. > 토폴로지에 보관 서버를 추가 하는 경우 토폴로지 작성기는 보관 파일 저장소를 설정 하 고 파일 저장소에 사용할 파일 공유에 대 한 Dacl (임의 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유의 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)를 참조하세요. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서에서 [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하세요.


