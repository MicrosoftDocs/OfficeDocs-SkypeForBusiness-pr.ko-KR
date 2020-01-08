---
title: 'Lync Server 2013: Lync Server 하이브리드 환경 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="5744e-102">Lync Server 2013 하이브리드 환경 개요</span><span class="sxs-lookup"><span data-stu-id="5744e-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5744e-103">_**마지막으로 수정한 주제:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="5744e-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="5744e-104">Lync Server 2013 하이브리드 환경에서는 일부 사용자가 온-프레미스 Lync Server 2013에 있고 다른 사용자가 Lync Online에 속해 있지만, 사용자가 동일한 도메인 (예: user@contoso.com)을 공유 하는 배포를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="5744e-105">가이드 정보</span><span class="sxs-lookup"><span data-stu-id="5744e-105">About this Guide</span></span>

<span data-ttu-id="5744e-106">이 가이드에서는 lync Online과의 상호 운용성을 위해 Lync Server 2013 환경을 구성 하는 데 필요한 작업을 설명 하 고 Lync Online을 사용 하도록 온-프레미스 배포의 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="5744e-107">필요 조건</span><span class="sxs-lookup"><span data-stu-id="5744e-107">Prerequisites</span></span>

<span data-ttu-id="5744e-108">하이브리드 배포를 구성 하기 위한 작업을 완료 하려면 다음 응용 프로그램과 유틸리티가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="5744e-109">이러한 파일의 설치 관리자는 배포에 대해 제공 되는 설치 미디어와 다음 목록에 포함 된 링크에도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="5744e-110">AD FS (Active Directory Federation Services) 2.0</span><span class="sxs-lookup"><span data-stu-id="5744e-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="5744e-111">Microsoft 디렉터리 동기화 도구 9.1</span><span class="sxs-lookup"><span data-stu-id="5744e-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="5744e-112">AD FS를 사용 하 여 single sign-on 용 Windows PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="5744e-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="5744e-113">Microsoft Online Services 로그인 도우미 (msoidcli-)는 office 365 관리 포털에서 연결 된 다운로드 페이지에서 구할 수 있는 Office 365 데스크톱 설정에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="5744e-114">관리자 자격 증명</span><span class="sxs-lookup"><span data-stu-id="5744e-114">Administrator Credentials</span></span>

<span data-ttu-id="5744e-115">관리자 자격 증명을 제공 하 라는 메시지가 표시 되 면 Office 365 테 넌 트의 관리자 계정에 대 한 사용자 이름 및 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="5744e-116">AD FS (Active Directory Federation Services) 2.0, 디렉터리 동기화, Single sign-on, 페더레이션 및 사용자 이동을 Lync Online으로 구성 하는 경우에도 이러한 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="5744e-117">Lync Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="5744e-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="5744e-118">이제 관리자는 Windows PowerShell을 사용 하 여 Lync Online 및 Lync Online 사용자 계정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="5744e-119">이렇게 하려면 먼저 Microsoft 다운로드 센터 ()http://go.microsoft.com/fwlink/?LinkId=294688)에서 Lync Online 커넥터 모듈을 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5744e-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="5744e-120">Lync Online 커넥터 모듈을 다운로드 하 고 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 windows powershell을 사용 하 여 lync online 관리에 대 한 자세한 [내용을 참조 하세요](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5744e-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

