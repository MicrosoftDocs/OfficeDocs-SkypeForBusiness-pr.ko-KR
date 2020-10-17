---
title: 'Lync Server 2013: 글로벌 호스팅된 음성 메일 정책 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a7e9dcb3c626c076d51fa32fa195f0787a922c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515175"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="58e9c-102">Lync Server 2013에서 호스팅된 글로벌 음성 메일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="58e9c-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58e9c-103">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="58e9c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="58e9c-104">*글로벌* 호스팅된 음성 메일 정책은 Lync Server 2013와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="58e9c-105">필요에 맞게 수정할 수는 있지만 이름을 바꾸거나 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="58e9c-106">전역 정책을 수정 하려면 Set-CsHostedVoicemailPolicy cmdlet을 사용 하 여 특정 배포에 대 한 적절 한 값으로 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="58e9c-107">[Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="58e9c-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="58e9c-108">글로벌 호스팅된 음성 메일 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="58e9c-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="58e9c-109">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="58e9c-110">Set-CsHostedVoicemailPolicy cmdlet을 실행 하 여 환경에 대 한 전역 정책 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="58e9c-111">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="58e9c-112">이 명령은 정책의 Identity 매개 변수를 지정 하지 않으므로 Windows PowerShell 명령줄 인터페이스는 글로벌 호스팅된 음성 메일 정책에서 다음 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="58e9c-p103">**Destination**은 호스팅된 Exchange UM 서비스의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 매개 변수는 선택 사항이지만 호스팅된 음성 메일에 대해 사용자를 활성화하려는 경우 사용자에게 할당된 정책에 Destination 값이 없으면 활성화가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="58e9c-115">**조직** 홈 Lync Server 사용자가 사용 하는 쉼표로 구분 된 Exchange 테 넌 트 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="58e9c-116">각 테넌트는 호스트된 Exchange UM 서비스에 있는 해당 테넌트의 FQDN으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="58e9c-117">이전 예제 cmdlet에서 "corp1.litwareinc.com" 값은 조직 매개 변수에 이미 있을 수 있는 모든 값을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="58e9c-118">예를 들어 정책에 이미 쉼표로 구분 된 조직 목록이 포함 되어 있는 경우 전체 목록이 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="58e9c-119">전체 목록을 대체 하는 대신 목록에 조직을 추가 하려면 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e9c-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

