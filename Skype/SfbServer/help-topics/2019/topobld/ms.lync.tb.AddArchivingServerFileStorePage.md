---
title: 보관 서버 파일 저장소 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
ROBOTS: NOINDEX, NOFOLLOW
description: IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두에 대한 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(FQDN) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 2e8c4ac23ce68eab111bbb7775eec23aba2f12d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100234"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="8fcdb-104">보관 서버 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="8fcdb-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="8fcdb-105">IM(인스턴트 메시징) 및 웹 회의(모임) 콘텐츠 모두에 대한 보관을 사용하도록 설정하려면 모든 웹 회의 콘텐츠의 복사본에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-105">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content.</span></span> <span data-ttu-id="8fcdb-106">보관 파일 저장소에 기존 파일 공유를 사용할 수도 있습니다. 또는 파일 공유가 위치할 파일 서버의 FQDN(FQDN) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-106">You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fcdb-107">파일 공유를 만들기 전에 토폴로지 작성기에서 파일 공유를 정의할 수 있지만 토폴로지를 게시하기 전에 정의된 위치에 파일 공유를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="8fcdb-108">> 토폴로지에서 보관 서버를 추가할 때 토폴로지 작성기에서 보관 파일 저장소를 설정하고 파일 저장소에 사용할 파일 공유에 대한 DACL(사용자별 액세스 제어 목록)을 구성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="8fcdb-109">이렇게 하려면 토폴로지 작성기를 실행하여 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="8fcdb-110">파일 공유의 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 File [Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) 및 배포 [설명서의 SQL Server Data and Log File Placement를](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="8fcdb-111">파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fcdb-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>