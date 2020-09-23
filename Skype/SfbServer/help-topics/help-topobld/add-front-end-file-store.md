---
title: 프런트 엔드 파일 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 4e2c732e0003f23cf183374880592ccd24fbe9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218349"
---
# <a name="add-front-end-file-store"></a>프런트 엔드 파일 저장소 추가

Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> Enterprise Edition 프런트 엔드 서버에는 파일 공유를 배치할 수 없지만 Standard Edition 서버에는 배치할 수 있습니다.

> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의한, 정의된 위치에 파일 공유를 만들어야 합니다.

> [!IMPORTANT]
> 엔터프라이즈 프런트 엔드 풀 또는 Standard Edition server를 토폴로지에 추가할 때 토폴로지 작성기는 파일 저장소를 설정 하 고 파일 저장소에 사용할 파일 공유에 대 한 Dacl (임의 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유를 위한 저장소 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [파일 저장소 지원](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하십시오. Enterprise Edition 프런트 엔드 풀에 대한 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [프런트 엔드 풀 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)을 참조하십시오.


