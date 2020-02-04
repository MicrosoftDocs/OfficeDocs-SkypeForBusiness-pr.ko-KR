---
title: 디렉터 파일 저장소 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: 디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.
ms.openlocfilehash: 14132f15d82bbe5b671a66fc740f5c8a2eee747c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703193"
---
# <a name="add-director-file-store"></a><span data-ttu-id="81bcf-104">디렉터 파일 저장소 추가</span><span class="sxs-lookup"><span data-stu-id="81bcf-104">Add Director File Store</span></span>

<span data-ttu-id="81bcf-p102">디렉터에 대한 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81bcf-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81bcf-p103">토폴로지에 디렉터를 추가하면 토폴로지를 게시할 때 파일 저장소를 설정하고 파일 저장소로 사용할 파일 공유에 대한 DACL(임의 액세스 제어 목록)을 구성하기 위한 적절한 권한이 필요합니다. 이렇게 하려면 토폴로지 작성기를 실행하고 새 토폴로지를 게시할 때 파일 공유에 대한 모든 권한(읽기/쓰기/수정)을 가진 계정으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81bcf-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="81bcf-p104">파일 공유를 위한 저장소 지원에 대한 자세한 내용은 지원 가능성 설명서의 [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) 및 배포 설명서의 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)를 참조하세요. 파일 공유 배치에 대한 자세한 내용은 지원 가능성 설명서의 [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)를 참조하세요. 디렉터용 토폴로지를 디자인하는 방법에 대한 자세한 내용은 배포 설명서의 [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81bcf-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation. For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


