---
title: 디렉터 파일 저장소 추가
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
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: 디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 4c68e592568f160575433d5b4f772eadf8c81a2e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215539"
---
# <a name="add-director-file-store"></a><span data-ttu-id="b3eac-104">디렉터 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="b3eac-104">Add Director File Store</span></span>

<span data-ttu-id="b3eac-p102">디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3eac-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3eac-p103">토폴로지에 디렉터를 추가하면 토폴로지를 게시할 때 파일 저장소를 설정하고 파일 저장소로 사용할 파일 공유에 대한 DACL(임의 액세스 제어 목록)을 구성하기 위한 적절한 권한이 필요합니다. 이렇게 하려면 토폴로지 작성기를 실행하고 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3eac-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="b3eac-109">파일 공유를 위한 저장소 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [파일 저장소 지원](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3eac-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="b3eac-110">파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [지원되는 서버 배치](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3eac-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="b3eac-111">디렉터용 토폴로지를 디자인하는 방법에 대한 자세한 내용은 배포 설명서에서 [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3eac-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


