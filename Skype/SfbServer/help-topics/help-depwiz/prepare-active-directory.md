---
title: Active Directory 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: 비즈니스용 Skype 서버 2015 설치를 시작하려면 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다. 비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내하며, 이 단계를 시작하여 포리스트 준비에 대해 안내합니다. Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.
ms.openlocfilehash: 9a741e56166d3235096a154bc2ef86770409adb9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804838"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="5b62b-105">Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="5b62b-105">Prepare Active Directory</span></span>

<span data-ttu-id="5b62b-106">비즈니스용 Skype 서버 2015 설치를 시작하려면 서버 및 사용자를 호스팅할 Active Directory 도메인 서비스, 포리스트 및 도메인을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b62b-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="5b62b-107">비즈니스용 Skype 서버 배포 마법사는 Active Directory를 준비하는 데 필요한 단계를 안내하며, 이 단계를 시작하여 포리스트 준비에 대해 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="5b62b-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="5b62b-108">Active Directory 복제가 성공적이면 사용자 또는 서버를 호스팅할 각 도메인을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="5b62b-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b62b-p103">스키마를 성공적으로 준비하려면 Enterprise Admins 그룹 및 Schema Admins 그룹의 구성원으로 로그인해야 합니다. 포리스트를 준비하려면 Enterprise Admins 그룹의 구성원으로 로그인하거나 포리스트 루트에서 관리자로 로그인해야 합니다. 도메인 준비를 위해서는 Domain Admins 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b62b-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="5b62b-112">지원되는 Active Directory 토폴로지에 대한 자세한 내용은 지원 가능성 설명서에서 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b62b-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="5b62b-113">Active Directory 준비에 대한 자세한 내용은 배포 설명서에서 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b62b-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


