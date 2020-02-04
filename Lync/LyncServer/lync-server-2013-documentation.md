---
title: 'Lync Server 2013: 문서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaeb06f1d9144d0c6f28984d509b3777673e10f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="a5e14-102">Lync Server 2013의 설명서</span><span class="sxs-lookup"><span data-stu-id="a5e14-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5e14-103">_**마지막으로 수정한 주제:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a5e14-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a5e14-104">MOF 모델은 여러 서비스 관리 기능으로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="a5e14-105">작업을 수행 하는 방법과 시기에 대 한 설명서는 같은 팀의 구성원 또는 다른 팀과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="a5e14-106">문서를 저장 하 고 공유 하는 방법은 함수 유형에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="a5e14-107">예를 들어 시스템 관리 절차는 자주 인쇄 되 고 참조 될 가능성이 있으므로 Word 문서로 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="a5e14-108">구성 관리 정보는 쉽게 검색 하 고 인덱싱할 수 있도록 자동으로 생성 되 고 데이터베이스에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="a5e14-109">일부 문서는 중요 한 것 이며 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="a5e14-110">문서 관리 시스템</span><span class="sxs-lookup"><span data-stu-id="a5e14-110">Document management systems</span></span>

<span data-ttu-id="a5e14-111">설명서 관리 시스템은 문서에 대 한 중앙 리포지토리 역할을 하 고 문서의 최신 수정 버전만 사용할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="a5e14-112">참조를 위해 이전 버전의 문서를 보관 하는 것도 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="a5e14-113">Lync Server는이 작업에 적합 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a5e14-114">Databases</span><span class="sxs-lookup"><span data-stu-id="a5e14-114">Databases</span></span>

<span data-ttu-id="a5e14-115">여러 도구와 관리 기능에 대 한 자세한 내용은 데이터베이스 사용에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="a5e14-116">구성 관리 프로세스는 인덱싱과 검색을 필요로 하는 많은 양의 데이터를 저장 하는 자동화 된 프로세스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="a5e14-117">지원 담당자는 새로운 문제를 해결할 때 이전 문제와 해결 방법을 데이터베이스에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="a5e14-118">다른 목적으로 서로 다른 데이터베이스를 사용 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="a5e14-119">이러한 데이터베이스의 연결 또는 결합 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="a5e14-120">예를 들어 서비스 데스크에서 일반적인 테마와 관련 된 여러 문제 (예: 특정 네트워크 어댑터의 문제를 일으키는 새 소프트웨어)를 식별 하는 경우 지원 담당자가 구성 데이터베이스를 쿼리하여 영향을 받을 수 있는 컴퓨터 수를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e14-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

