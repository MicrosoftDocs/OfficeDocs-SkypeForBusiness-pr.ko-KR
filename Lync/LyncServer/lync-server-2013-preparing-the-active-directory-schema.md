---
title: 'Lync Server 2013: Active Directory 스키마 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506855"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="673d4-102">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="673d4-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="673d4-103">_**마지막으로 수정 된 항목:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="673d4-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="673d4-104">Active Directory 도메인 서비스 준비를 시작 하기 전에 Windows 메모장과 같은 텍스트 편집기를 사용 하 여 스키마 파일을 열거나 lync [server 2013에서 사용 하는 Active directory 스키마 확장, 클래스 및 특성](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) 을 확인 하 여 lync server 2013에 대해 수정 될 모든 Active Directory 도메인 서비스 스키마 확장을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="673d4-105">Lync Server에서는 다음과 같은 네 개의 스키마 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="673d4-106">Microsoft Exchange Server와의 상호 운용성을 위해 사용 되는 ExternalSchema .ldf</span><span class="sxs-lookup"><span data-stu-id="673d4-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="673d4-107">기본 Lync Server 2013 스키마 파일인 ServerSchema .ldf</span><span class="sxs-lookup"><span data-stu-id="673d4-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="673d4-108">BackCompatSchema.ldf - 이전 릴리스 구성 요소와의 상호 운용성을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="673d4-109">VersionSchema.ldf - 준비된 스키마의 버전 정보에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="673d4-110">모든 .ldf 파일은 이전 릴리스에서 마이그레이션하든, 새 설치를 수행하든 관계없이 스키마 준비 중에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="673d4-111">이러한 스키마 파일은 앞의 목록에 표시 된 순서 대로 설치 되며 \\ \\ 설치 미디어의 지원 스키마 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="673d4-112">Lync Server 스키마 확장은 네트워크 트래픽에 영향을 주는 모든 도메인에서 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="673d4-113">따라서 스키마 준비는 네트워크 사용량이 적을 때 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="673d4-114">Microsoft® Office Communicator Mobile 2007 R2 for Java 및 Microsoft® Office Communicator Mobile for Nokia 1.0 모바일 클라이언트를 Lync Server 2013 배포에 추가 해야 하는 경우 Lync Server 2013을 설치 하는 동안 Microsoft Office Communications Server 2007 r 2에 대 한 Active Directory 스키마를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="673d4-115">필요한 소프트웨어 및 설명서는를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .</span><span class="sxs-lookup"><span data-stu-id="673d4-115">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="673d4-116">ADSI 편집</span><span class="sxs-lookup"><span data-stu-id="673d4-116">ADSI Edit</span></span>

<span data-ttu-id="673d4-117">ADSI 편집(Active Directory 서비스 인터페이스 편집기)은 스키마 준비 및 복제를 확인하는 데 사용할 수 있는 AD DS 관리 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="673d4-118">서버를 도메인 컨트롤러로 만들기 위해 AD DS 역할을 설치할 때 ADSI 편집이 기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="673d4-119">Windows Server 2008 및 Windows Server 2008 r 2의 경우 RSAT (원격 서버 관리 도구)에 ADSI 편집 (adsiedit)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="673d4-120">RSAT를 도메인 구성원 서버 또는 독립 실행형 서버에 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="673d4-121">RSAT 패키지는 Windows를 설치할 때 이러한 서버에 기본적으로 복사되지만, 기본적으로 설치되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="673d4-122">서버 관리자를 사용하여 개별 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="673d4-123">ADSI 편집은 **역할 관리 도구**, **Active Directory 도메인 서비스 도구** 및 **Active Directory 도메인 컨트롤러 도구**에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="673d4-124">Windows Server 2003의 경우 ADSI 편집은 지원 도구에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="673d4-125">지원 도구는 Windows Server 2003 CD의 \\ 지원 \\ 도구 폴더에서 제공 되거나 "windows Server 2003 서비스 팩 2 32 비트 지원 도구"에서 다운로드할 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) .</span><span class="sxs-lookup"><span data-stu-id="673d4-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="673d4-126">제품 CD에서 지원 도구를 설치 하는 방법에 대 한 자세한 내용은의 "Windows 지원 도구 설치"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) 하십시오.</span><span class="sxs-lookup"><span data-stu-id="673d4-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="673d4-127">Adsiedit.dll은 지원 도구를 설치할 때 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="673d4-128">그러나 이 파일을 컴퓨터에 그냥 복사한 경우에는 도구를 실행하기 전에 **regsvr32** 명령을 실행하여 adsiedit.dll 파일을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="673d4-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="673d4-129">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="673d4-129">In This Section</span></span>

  - [<span data-ttu-id="673d4-130">Lync Server 2013에서 Active Directory 스키마 준비 실행</span><span class="sxs-lookup"><span data-stu-id="673d4-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="673d4-131">Lync Server 2013에서 Active Directory 스키마 복제 확인</span><span class="sxs-lookup"><span data-stu-id="673d4-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="673d4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="673d4-132">See Also</span></span>


[<span data-ttu-id="673d4-133">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="673d4-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="673d4-134">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="673d4-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

