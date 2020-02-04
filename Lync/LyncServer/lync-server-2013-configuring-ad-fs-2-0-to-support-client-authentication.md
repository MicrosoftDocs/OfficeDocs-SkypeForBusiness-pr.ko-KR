---
title: 'Lync Server 2013: 클라이언트 인증을 지원 하도록 AD FS 2.0 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="3a313-102">Lync Server 2013에서 클라이언트 인증을 지원 하도록 AD FS 2.0 구성</span><span class="sxs-lookup"><span data-stu-id="3a313-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a313-103">_**마지막으로 수정한 주제:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="3a313-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="3a313-104">AD FS 2.0에서 스마트 카드를 사용 하 여 인증을 지원 하도록 구성할 수 있는 인증 유형에는 두 가지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="3a313-105">FBA (양식 기반 인증)</span><span class="sxs-lookup"><span data-stu-id="3a313-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="3a313-106">전송 계층 보안 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="3a313-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="3a313-107">폼 기반 인증을 사용 하 여 사용자 이름/암호를 사용 하거나 스마트 카드 및 PIN을 사용 하 여 인증할 수 있는 웹 페이지를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="3a313-108">이 항목에서는 AD FS 2.0를 사용 하 여 전송 계층 보안 클라이언트 인증을 구현 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="3a313-109">AD FS 2.0 인증 형식에 대 한 자세한 내용은 AD FS 2.0:에서 [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)로컬 인증 유형을 변경 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a313-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="3a313-110">**클라이언트 인증을 지원 하도록 AD FS 2.0를 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="3a313-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="3a313-111">도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="3a313-112">Windows 탐색기를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="3a313-113">C:\\inetpub\\adf\\ls로 이동</span><span class="sxs-lookup"><span data-stu-id="3a313-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="3a313-114">기존 web.config 파일의 백업 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="3a313-115">메모장을 사용 하 여 기존 web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="3a313-116">메뉴 모음에서 **편집** 을 선택 하 고 **찾기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="3a313-117">\*\* \<Localauthenticationtypes\>\*\* 를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="3a313-118">4 개의 인증 유형이 한 줄당 하나씩 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="3a313-119">TLSClient 인증 형식이 포함 된 줄을 섹션의 목록 맨 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="3a313-120">Web.config 파일을 저장 하 고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="3a313-121">관리자 권한으로 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="3a313-122">다음 명령을 실행 하 여 IIS를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a313-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

