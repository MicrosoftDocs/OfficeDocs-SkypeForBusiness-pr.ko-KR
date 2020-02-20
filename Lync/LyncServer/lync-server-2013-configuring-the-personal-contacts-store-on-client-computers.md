---
title: 'Lync Server 2013: 클라이언트 컴퓨터에서 개인 연락처 저장소 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e035c360d339b48157969c75a1702beff03da634
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="e9829-102">클라이언트 컴퓨터에서 Lync Server 2013의 개인 연락처 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="e9829-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9829-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e9829-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e9829-104">Microsoft Lync Server 2013와 Microsoft Exchange Server 2013를 통합 하는 경우 Microsoft Lync 2010을 실행 하는 모든 클라이언트 컴퓨터에서 개인 연락처 저장소를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="e9829-105">특히 Exchange를 개인 연락처 저장소로 사용 하도록 Lync를 구성 하 고, 동시에 사용자가 해당 의사 결정을 재정의할 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="e9829-106">각 클라이언트 컴퓨터에서 레지스트리 값을 만들고 구성 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="e9829-107">Lync 2013을 실행 하는 컴퓨터에는이 매개 변수를 입력 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="e9829-108">단일 컴퓨터에서이 값을 구성 하려면 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="e9829-109">클라이언트 컴퓨터에서 **시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="e9829-110">**실행** 대화 상자에 regedit를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="e9829-111">레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **소프트웨어**, **정책**, **Microsoft**를 차례로 확장 한 다음 **Communicator**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="e9829-112">**Communicator**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **DWORD (32 비트) 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="e9829-113">새 값을 만든 후에 **PersonalContactStoreOverride** 를 입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="e9829-114">PersonalContactStoreOverride의 값이 0으로 설정 되어 있는지 확인 한 다음 레지스트리 편집기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="e9829-115">여러 컴퓨터에서 동일 하 게 변경 해야 하는 경우에는 사용자 지정 그룹 정책 개체를 만들어이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9829-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="e9829-116">자세한 내용은 그룹 정책 설명서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span><span class="sxs-lookup"><span data-stu-id="e9829-116">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

