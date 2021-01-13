---
title: Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '요약: 레거시 클라이언트에서 사용하는 개인 연락처 저장소를 구성합니다.'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833938"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="de191-103">Lync 2010 클라이언트 컴퓨터에서 개인 연락처 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="de191-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="de191-104">비즈니스용 Skype 서버 2015 및 Exchange Server 2016 또는 Exchange Server 2013을 통합하는 경우 클라이언트에서 사용하는 개인 연락처 저장소를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de191-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="de191-105">특히 Exchange를 개인 연락처 저장소로 사용하도록 비즈니스용 Skype를 구성하고 동시에 사용자가 해당 결정을 다시울 수 없는지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de191-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="de191-106">각 클라이언트 컴퓨터에서 레지스트리 값을 만들고 구성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de191-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de191-107">다음 절차는 Lync 2010 클라이언트를 사용하는 클라이언트에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de191-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="de191-108">Lync 2013 클라이언트 및 모든 비즈니스용 Skype 클라이언트에는 연락처 저장소 설정을 다시우는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de191-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="de191-109">단일 컴퓨터에서 이 값을 구성하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="de191-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="de191-110">클라이언트 컴퓨터에서 시작을  클릭한 다음 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de191-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="de191-111">**실행** 대화 상자에 regedit를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="de191-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="de191-112">레지스트리 편집기에서 **HKEY_LOCAL_MACHINE,** 소프트웨어 **확장,** 정책 **확장,** **Microsoft** 확장 및 **Communicator.**</span><span class="sxs-lookup"><span data-stu-id="de191-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="de191-113">새 **Communicator** 마우스 오른쪽 단추로 클릭한 다음 **DWORD(32비트) 값을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de191-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="de191-114">새 값을 만든 후 PersonalContactStoreOverride를 입력한 다음 Enter를 눌러 값 이름을 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de191-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="de191-115">PersonalContactStoreOverride의 값이 0으로 설정되어 있는지 확인한 다음 레지스트리 편집기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="de191-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="de191-116">여러 컴퓨터에서 동일한 변경을 해야 하는 경우 사용자 지정 그룹 정책 개체를 만들어서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de191-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="de191-117">Windows 10에서 이 작업을 수행하기 위한 자세한 내용은 그룹 정책 개체 만들기 [문서를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="de191-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
