---
title: 'Lync Server 2013: Kerberos 인증 계정 암호 설정'
description: 'Lync Server 2013: Kerberos 인증 계정 암호를 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577224"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="6b042-103">Lync Server 2013에서 Kerberos 인증 계정 암호 설정</span><span class="sxs-lookup"><span data-stu-id="6b042-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b042-104">_**마지막으로 수정 된 항목:** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="6b042-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="6b042-105">Kerberos 인증 계정에 대 한 컴퓨터 개체를 만든 후에는 해당 계정의 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="6b042-106">Windows PowerShell cmdlet을 실행 하 여 한 서버에서 Kerberos 계정 암호를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="6b042-107">Kerberos 인증을 위해 만든 개체에 대해 암호를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="6b042-108">암호는 알려진 값으로 설정할 수 있지만 기본적으로 임의의 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="6b042-109">암호는 해당 계정을 사용 하는 모든 Kerberos 인증 원본에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="6b042-110">Windows PowerShell cmdlet을 사용 하 여 Kerberos 계정 암호를 설정 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b042-111">Kerberos account 개체는 computer 개체 이지만 참조 되는 Windows PowerShell cmdlet의 작업에는 Useraccount 지만 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="6b042-112">이는 실수는 아니지만 Kerberos 계정 만들기 및 유지 관리와 함께 사용할 때 cmdlet이 의도 한 동작을 나타내는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b042-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b042-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6b042-113">In This Section</span></span>

  - [<span data-ttu-id="6b042-114">Lync Server 2013에서 서버에 대해 Kerberos 인증 계정 암호 설정</span><span class="sxs-lookup"><span data-stu-id="6b042-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="6b042-115">Lync Server 2013에서 IIS에 Kerberos 인증 계정 암호 동기화</span><span class="sxs-lookup"><span data-stu-id="6b042-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

