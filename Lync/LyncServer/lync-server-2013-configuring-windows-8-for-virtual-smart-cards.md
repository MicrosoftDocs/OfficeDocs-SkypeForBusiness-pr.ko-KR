---
title: 'Lync Server 2013: 가상 스마트 카드에 대해 Windows 8 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10cedd0162b5d7680d3aadd016fbcb8ea87e0d67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="032d1-102">Lync Server 2013를 사용 하 여 가상 스마트 카드를 사용 하도록 Windows 8 구성</span><span class="sxs-lookup"><span data-stu-id="032d1-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="032d1-103">_**마지막으로 수정 된 항목:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="032d1-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="032d1-104">2 단계 인증 및 스마트 카드 기술을 배포할 때 고려해 야 하는 한 가지 요인은 구현 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="032d1-105">Windows 8에서는 새로운 여러 보안 기능을 제공 하며, 가장 흥미로운 새로운 기능 중 하나는 가상 스마트 카드에 대 한 지원입니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="032d1-106">규정 버전 1.2을 충족 하는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 설치 된 컴퓨터의 경우 조직은 하드웨어에 추가 투자 없이 스마트 카드 로그온 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="032d1-107">자세한 내용은 Windows 8에서 [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365)가상 스마트 카드 사용을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="032d1-107">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="032d1-108">가상 스마트 카드에 대해 Windows 8을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="032d1-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="032d1-109">Lync 사용 가능 사용자의 자격 증명을 사용 하 여 Windows 8 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="032d1-110">Windows 8 시작 화면에서 커서를 화면의 오른쪽 아래 모서리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="032d1-111">**검색** 옵션을 선택한 다음 **명령 프롬프트**를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="032d1-112">**명령 프롬프트**를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="032d1-113">다음 명령을 실행 하 여 TPM (신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="032d1-114">TPM 관리 콘솔에서 TPM 사양 버전이 1.2 이상 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="032d1-115">호환 되는 TPM (트러스트 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 표시 되 면 컴퓨터에 호환 되는 TPM 모듈이 있고 시스템 BIOS에서 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="032d1-116">TPM 관리 콘솔 닫기</span><span class="sxs-lookup"><span data-stu-id="032d1-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="032d1-117">명령 프롬프트에서 다음 명령을 사용 하 여 새 가상 스마트 카드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="032d1-118">가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공 하려면 대신/tpin 프롬프트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="032d1-119">명령 프롬프트에서 다음 명령을 실행 하 여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="032d1-120">컴퓨터 관리 콘솔에서 **장치 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="032d1-121">**스마트 카드 판독기**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="032d1-122">새 가상 스마트 카드 판독기가 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="032d1-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

