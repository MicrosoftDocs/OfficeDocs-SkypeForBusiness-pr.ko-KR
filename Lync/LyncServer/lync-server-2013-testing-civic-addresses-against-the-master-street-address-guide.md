---
title: 마스터 주소 가이드에 대해 도심 주소 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f9115e6bc0c65f589effc08ecd5f7b681208a54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="c9871-102">Lync Server 2013의 마스터 주소 가이드에 대 한 도심 주소 테스트</span><span class="sxs-lookup"><span data-stu-id="c9871-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9871-103">_**마지막으로 수정 된 항목:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c9871-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9871-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="c9871-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c9871-105">매일</span><span class="sxs-lookup"><span data-stu-id="c9871-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9871-106">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="c9871-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c9871-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9871-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9871-108">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="c9871-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c9871-109">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c9871-110">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsRegistration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="c9871-111">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c9871-112">설명</span><span class="sxs-lookup"><span data-stu-id="c9871-112">Description</span></span>

<span data-ttu-id="c9871-113">Test-csliscivicaddress cmdlet은 LIS (위치 정보 서비스) 데이터베이스에 추가 된 위치를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="c9871-114">이 cmdlet은 E9-1-1 네트워크 라우팅 공급자에 속한 MSAG (마스터 주소 가이드)에서 찾은 위치에 대해 위치를 비교 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="c9871-115">네트워크 라우팅 공급자가 없거나 공급자에 연결할 수 없는 경우 테스트가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="c9871-116">명령에 optional 스위치 매개 변수 UpdateValidationStatus를 추가 하는 경우 테스트를 통과 하는 각 주소에 대해 해당 MSAGValid database 속성이 True로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c9871-117">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="c9871-117">Running the test</span></span>

<span data-ttu-id="c9871-118">Test-csliscivicaddress cmdlet을 사용 하 여 개별 주소를 테스트 하거나 여러 주소를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="c9871-119">예를 들어이 명령은 Redmond, WA에 있는 단일 주소를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="c9871-120">비교를 통해이 명령은 LIS 데이터베이스에 있는 현재 모든 주소를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="c9871-121">자세한 내용은 [테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet에 대 한 도움말 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9871-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c9871-122">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="c9871-122">Determining success or failure</span></span>

<span data-ttu-id="c9871-123">Test-csliscivicaddress는 제공 된 주소에 대 한 성공 또는 실패를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="c9871-124">주소를 찾을 수 없거나 서비스 공급자에 연결할 수 없는 경우 주소 테스트에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c9871-125">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="c9871-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="c9871-126">다음은 Test-csliscivicaddress에서 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="c9871-127">LIS 서비스 공급자를 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="c9871-128">Export-cslisconfiguration cmdlet을 실행 하 여 LIS 서비스 공급자의 URL을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="c9871-129">그런 다음 해당 URL에 ping을 사용 하 여 서비스 공급자가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9871-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

