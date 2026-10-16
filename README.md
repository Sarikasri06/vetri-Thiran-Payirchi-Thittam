function validateLaptopRequest(request) {
    if (!request || !request.requester) {
        return {
            valid: false,
            message: "Requester is required."
        };
    }

    if (request.laptopType !== "standard") {
        return {
            valid: false,
            message: "Only standard laptop orders are supported."
        };
    }

    return {
        valid: true,
        message: "Request is ready for approval.",
        status: "Pending Approval"
    };
}

const request = {
    requester: "employee@example.com",
    laptopType: "standard"
};

console.log(validateLaptopRequest(request));
