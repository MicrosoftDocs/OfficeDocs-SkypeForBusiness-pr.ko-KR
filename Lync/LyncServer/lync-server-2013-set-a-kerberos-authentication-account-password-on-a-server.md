---
title: 'Lync Server 2013: 서버에서 Kerberos 인증 계정 암호 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="8e909-102">Lync Server 2013에서 서버에 대해 Kerberos 인증 계정 암호 설정</span><span class="sxs-lookup"><span data-stu-id="8e909-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e909-103">_**마지막으로 수정 된 항목:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="8e909-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="8e909-104">이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="8e909-105">프런트 엔드 서버, Standard Edition 서버 및 디렉터를 포함 하는 각 사이트의 Kerberos 계정에 대해 암호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="8e909-106">사이트의 한 서버 (예: 프런트 엔드 서버 1 개)에서 **c44er4osaccountpassword** Windows PowerShell cmdlet을 실행 하 여 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="8e909-107">각 사이트에 대해 **c44er4osaccountpassword** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="8e909-108">이 cmdlet은 웹 서비스 서비스에 대 한 IIS (인터넷 정보 서비스)를 구성한 다음 Active Directory 도메인 서비스의 컴퓨터 계정에 대 한 암호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="8e909-109">Cmdlet에서 사용 되는 매개 변수를 기반으로 하는 대체 방법은 Kerberos 계정 암호의 원본으로 구성 된 다른 서버를 사용 하는 동안 한 서버에서 IIS를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="8e909-110">**C4eercosaccountpassword** cmdlet을 사용 하 여 암호를 설정 하는 경우 Kerberos는 임의로 생성 된 문자열로 암호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="8e909-111">이 cmdlet은이 계정이 할당 된 모든 Lync Server 2013 중앙 사이트의 모든 IIS 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="8e909-112">Kerberos 인증 계정에 대 한 암호를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8e909-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="8e909-113">Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 도메인 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8e909-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e909-115">명령줄에서 다음의 두 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="8e909-116">예:</span><span class="sxs-lookup"><span data-stu-id="8e909-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e909-117">도메인\사용자 형식을 사용하여 UserAccount 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="8e909-118">User@Domain 확장명 형식은 Kerberos 인증을 위해 만든 컴퓨터 개체를 참조 하는 데 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8e909-119">계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e909-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

