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
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두에 대해 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(정식 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: a35bf3f7c1ef066aec1139ab2e886073ab65e23b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807148"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="7455b-104">보관 서버 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="7455b-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="7455b-105">IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두의 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7455b-105">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content.</span></span> <span data-ttu-id="7455b-106">보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(정식 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7455b-106">You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7455b-107">파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의된 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7455b-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="7455b-108">> 토폴로지에 보관 서버를 추가할 때 토폴로지 작성기에서 보관 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대한 DACL(사용자 액세스 제어 목록)을 구성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7455b-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="7455b-109">이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7455b-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="7455b-110">파일 공유에 대한 저장소 지원에 [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 대한 자세한 내용은 지원 가능성 설명서의 파일 저장소 지원 및 배포 설명서의 [SQL Server 데이터](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 및 로그 파일 배치를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7455b-110">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="7455b-111">파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7455b-111">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


