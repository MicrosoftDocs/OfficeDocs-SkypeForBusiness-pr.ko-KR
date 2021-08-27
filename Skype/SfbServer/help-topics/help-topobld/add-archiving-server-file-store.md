---
title: 보관 서버 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두에 대한 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(FQDN) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 30289de74ffb3c699ea16d7b4aaaf271902f5ccd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581432"
---
# <a name="add-archiving-server-file-store"></a>보관 서버 파일 저장소 추가

IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두에 대한 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(FQDN) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.

> [!IMPORTANT]
> 파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의된 위치에 파일 공유를 만들어야 합니다. > 토폴로지에서 보관 서버를 추가할 때 토폴로지 작성기에서 보관 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대한 DACL(사용자별 액세스 제어 목록)을 구성할 수 있어야 합니다. 이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.

파일 공유에 대한 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 및 배포 설명서의 SQL Server Data and Log File [Placement를](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 참조하십시오. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)를 참조하십시오.