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
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: IM (인스턴트 메시징) 및 웹 회의 (모임) 콘텐츠를 모두 보관할 수 있도록 하려면 모든 웹 회의 콘텐츠의 복사본에 대 한 파일 저장소로 사용할 파일 공유를 지정 해야 합니다. 보관 파일 저장소에 대해 기존 파일 공유를 사용 하거나, 파일 공유 위치에 있는 파일 서버의 FQDN (정규화 된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정 하 여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 22f7de704b3d7a611d4601df4c14ed75f7466c1c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217429"
---
# <a name="add-archiving-server-file-store"></a>보관 서버 파일 저장소 추가

IM (인스턴트 메시징) 및 웹 회의 (모임) 콘텐츠를 모두 보관할 수 있도록 하려면 모든 웹 회의 콘텐츠의 복사본에 대 한 파일 저장소로 사용할 파일 공유를 지정 해야 합니다. 보관 파일 저장소에 대해 기존 파일 공유를 사용 하거나, 파일 공유 위치에 있는 파일 서버의 FQDN (정규화 된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정 하 여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의된 위치에 파일 공유를 만들어야 합니다. > 토폴로지에 보관 서버를 추가 하는 경우 토폴로지 작성기에서 보관 파일 저장소를 설정 하 고 파일 저장소에 사용할 파일 공유에 대 한 Dacl (임의 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유를 위한 저장소 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [파일 저장소 지원](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하십시오.


