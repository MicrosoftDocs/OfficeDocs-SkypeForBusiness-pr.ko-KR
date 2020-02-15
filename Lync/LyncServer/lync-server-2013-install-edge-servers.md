---
title: Lync Server 2013:에 지 서버 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2738367bbbf2c81d5d5b0d084fffa9e992410f18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="ca533-102">Lync Server 2013에 대 한에 지 서버 설치</span><span class="sxs-lookup"><span data-stu-id="ca533-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca533-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ca533-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ca533-104">Lync server 배포 마법사를 사용 하 여에 지 서버에 Lync Server 2013을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="ca533-105">각 에지 서버에서 배포 마법사를 실행하면 에지 서버를 설정하는 데 필요한 대부분의 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="ca533-106">에 지 서버에 Lync Server 2013을 배포 하려면 토폴로지 작성기를 실행 하 여에 지 서버 토폴로지를 정의 하 고 게시 한 다음에 지 서버에서 사용할 수 있는 미디어로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="ca533-107">자세한 내용은 [Lync server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) , [lync Server 2013 토폴로지 내보내기 및 edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca533-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="ca533-108">배포 마법사를 사용 하 여 각에 지 서버를 설치 하 고, 필요한 인증서를 설치 및 할당 하 고, 필요한 서비스를 시작한 후에는 [Lync server 2013의 외부 사용자 액세스에 대 한 지원 구성](lync-server-2013-configuring-support-for-external-user-access.md) 의 정보를 사용 하 여 설치를 완료 하 고, 외부 사용자 액세스를 사용 하도록 설정 및 구성 하 고, [lync server 2013에서 Edge 배포를 확인](lync-server-2013-verifying-your-edge-deployment.md) 하 여 서버 및 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ca533-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="ca533-109">에지 서버를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ca533-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="ca533-110">로컬 Administrators 그룹의 구성원 또는 그에 해당하는 사용자 권한이 있는 계정으로 에지 서버를 설치할 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="ca533-111">토폴로지 작성기를 사용 하 여 만들고 내보낸 후 외부 미디어에 복사 된 토폴로지 구성 파일을에 지 서버 (예: 토폴로지 구성 파일을 복사한 USB 드라이브에 액세스)에서 사용할 수 있는지 확인 한 다음 확인을 클릭 합니다. 파일을 복사한 네트워크 공유에 대 한 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="ca533-112">배포 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca533-p102">Microsoft Visual C++ 재배포 가능 파일을 설치해야 한다는 메시지가 표시되면 <STRONG>예</STRONG>를 클릭합니다. 다음 대화 상자에서 기본 <STRONG>설치 위치</STRONG>를 그대로 적용하거나 <STRONG>찾아보기</STRONG>를 클릭하여 다른 위치를 선택한 후에 <STRONG>설치</STRONG>를 클릭합니다. 그 다음 대화 상자에서 <STRONG>동의함</STRONG> 확인란을 선택하고 <STRONG>확인</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="ca533-116">배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="ca533-117">마법사에서 배포 상태를 확인하고 나면 **1단계. 로컬 구성 저장소 설치**에서 **실행**을 클릭하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="ca533-118">**중앙 관리 저장소의 로컬 복제본 구성** 대화 상자에서 **파일에서 가져오기(에지 서버에 권장)** 을 클릭하고 내보낸 토폴로지 파일이 있는 위치로 이동한 다음 .zip 파일을 선택하고 **열기**, **다음**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="ca533-119">배포 마법사가 구성 파일에서 구성 정보를 읽고 XML 구성 파일을 로컬 컴퓨터에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="ca533-120">**명령 실행** 프로세스가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="ca533-121">배포 마법사에서 **2 단계: Lync Server 구성 요소 설치 또는 제거** 를 클릭 하 여 로컬 컴퓨터에 저장 된 XML 구성 파일에 지정 된 lync server 2013 edge 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="ca533-122">설치를 완료 한 후에 Edge 인증서 설정의 정보를 사용 하 여 서비스를 시작 하기 전에 [Lync Server 2013에 대 한](lync-server-2013-set-up-edge-certificates.md) 필수 인증서를 설치 및 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca533-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

