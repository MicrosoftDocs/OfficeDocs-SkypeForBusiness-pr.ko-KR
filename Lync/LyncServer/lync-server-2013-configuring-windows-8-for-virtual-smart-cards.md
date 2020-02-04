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
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="4db49-102">Lync Server 2013에서 가상 스마트 카드를 사용 하도록 Windows 8 구성</span><span class="sxs-lookup"><span data-stu-id="4db49-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4db49-103">_**마지막으로 수정한 주제:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="4db49-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="4db49-104">2 단계 인증 및 스마트 카드 기술을 구축할 때 고려해 야 하는 한 가지 요인은 구현 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="4db49-105">Windows 8은 다양 한 새로운 보안 기능을 제공 하 고 가장 흥미로운 새 기능 중 하나는 가상 스마트 카드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="4db49-106">규정 버전 1.2을 충족 하는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 장착 된 컴퓨터의 경우, 이제 조직에서는 하드웨어에 대 한 추가 투자 없이 스마트 카드 로그온의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="4db49-107">자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)Windows 8과 함께 가상 스마트 카드 사용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4db49-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="4db49-108">가상 스마트 카드에 대해 Windows 8을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="4db49-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="4db49-109">Lync를 사용 하는 사용자의 자격 증명을 사용 하 여 Windows 8 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="4db49-110">Windows 8 시작 화면에서 화면 오른쪽 아래 모서리로 커서를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="4db49-111">**검색** 옵션을 선택한 다음 **명령 프롬프트**를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="4db49-112">**명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="4db49-113">다음 명령을 실행 하 여 TPM (신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="4db49-114">TPM 관리 콘솔에서 TPM 사양 버전이 최소 1.2 인지 확인</span><span class="sxs-lookup"><span data-stu-id="4db49-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4db49-115">호환 되는 TPM (신뢰할 수 있는 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 표시 되는 경우 컴퓨터에 호환 되는 TPM 모듈이 있고 시스템 BIOS에서 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="4db49-116">TPM 관리 콘솔을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="4db49-117">명령 프롬프트에서 다음 명령을 사용 하 여 새 가상 스마트 카드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4db49-118">가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공 하려면/cpin prompt를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="4db49-119">명령 프롬프트에서 다음 명령을 실행 하 여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="4db49-120">컴퓨터 관리 콘솔에서 **장치 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="4db49-121">**스마트 카드 판독기**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="4db49-122">새 가상 스마트 카드 판독기가 성공적으로 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db49-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

