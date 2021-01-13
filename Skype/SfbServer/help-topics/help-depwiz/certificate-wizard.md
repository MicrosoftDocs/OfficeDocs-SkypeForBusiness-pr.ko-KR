---
title: 인증서 마법사
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: 인증서를 요청, 할당, 제거 또는 보기하려면 인증서 마법사를 사용하면 됩니다. RTCUniversalServerAdmins 그룹의 구성원으로 로그인해야 합니다. 공용 CA(인증 기관)의 인증서를 요청하는 데에는 추가 그룹 구성원 자격이 필요하지 않습니다. 조직의 PKI(공개 키 인프라)에서 인증서를 요청하려면 필요한 추가 그룹 구성원 자격(있는 경우)을 확인해야 합니다. 요청 작업 중에 PKI의 발급 CA에서 인증서를 요청하는 데 사용할 대체 자격 증명을 입력할 수 있습니다.
ms.openlocfilehash: f8c21cf141d2145e7592a0615a32eafdfa8de10e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805088"
---
# <a name="certificate-wizard"></a><span data-ttu-id="a113c-107">마법사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-107">Certificate Wizard</span></span>
 
<span data-ttu-id="a113c-108">인증서를 **요청,** **할당,** 제거 또는  **확인하려면** 인증서 마법사를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="a113c-109">RTCUniversalServerAdmins 그룹의 구성원으로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="a113c-110">공용 CA(인증 기관)의 인증서를 요청하는 데에는 추가 그룹 구성원 자격이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="a113c-111">조직의 PKI(공개 키 인프라)에서 인증서를 요청하려면 필요한 추가 그룹 구성원 자격(있는 경우)을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="a113c-112">요청 작업 중에 PKI의 발급 CA에서 인증서를 요청하는 데 사용할 대체 자격 증명을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="a113c-113">새 인증서를 요청하려면 **요청** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="a113c-114">아직 할당되지 않은 인증서를 할당하려면 **할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="a113c-115">이전에 할당한 인증서를 제거하려면 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a113c-116">제거 **단추는** 인증서가 이전에 할당된 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-116">The **Remove** button will be available only if a certificate has been previously assigned.</span></span> <span data-ttu-id="a113c-117">제거 **단추를** 사용할 수 없는 경우(희미하게 표시) 할당된 인증서가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-117">If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="a113c-118">할당된 인증서를 보려면 **보기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a113c-119">보기 **단추는** 인증서가 이전에 할당된 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-119">The **View** button will be available only if a certificate has been previously assigned.</span></span> <span data-ttu-id="a113c-120">**보기** 단추가 회색으로 표시되면 할당된 인증서가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-120">If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="a113c-121">현재 인증서 할당 화면을 새로 고치려면 **새로 고침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="a113c-122">인증서 저장소에 없는 인증서를 가져오려면 **인증서 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a113c-123">**인증서 가져오기** 는 일반적으로 인증서 마법사에서의 요청이 아닌 프로세스를 통해 받은 인증서를 처리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="a113c-124">예를 들어 PKI 관리자가 인증서를 만들어 사용자가 해당 인증서를 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="a113c-125">인증서 **가져오기** 기능을 사용하여 인증서를 컴퓨터의 인증서 저장소로 가져오고 비즈니스용 Skype 서버에서 할당할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="a113c-126">조직에서 CA 관리자 승인이 필요한 CA의 인증서 요청을 요청하는 프로세스를 완료하려면 **대기 중인 요청 처리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-126">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**.</span></span> <span data-ttu-id="a113c-127">인증서 요청은 보류 중인 상태를 반환하고 보류 중인 요청의 ID 번호도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-127">The certificate request will have returned a status of pending, and also displays the identification number of the pending request.</span></span> <span data-ttu-id="a113c-128">대기 상태의 인증서를 계속해서 처리하려면 **새로 고침** 을 클릭하여 **대기 중인 요청 처리** 단추를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-128">To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button.</span></span> <span data-ttu-id="a113c-129">대기 **중인 요청 프로세스** 단추를 더 이상 사용할 수 없습니다(희미하게 표시).</span><span class="sxs-lookup"><span data-stu-id="a113c-129">The **Process Pending Request** button will no longer be unavailable (dimmed).</span></span> <span data-ttu-id="a113c-130">그러면 대기 중인 요청을 검색할 수 있지만 요청 상태는 CA 관리자가 인증서를 발급하거나 거부할 때까지 대기 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-130">You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator.</span></span> <span data-ttu-id="a113c-131">인증서 마법사에서 만든 올바른 대기 중인 요청이 없는 경우 이 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a113c-131">The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

