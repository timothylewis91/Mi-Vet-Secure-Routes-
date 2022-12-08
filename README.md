# Mi-Vet-Secure-Routes-

const getPage = (pageIndex, pageSize) => {
  const config = {
    method: "GET",
    url: `${API_HOST_PREFIX}/blogs?pageIndex=${pageIndex}&pageSize=${pageSize}`,
    withCredentials: true,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};

const getBy = (id) => {
  const config = {
    method: "GET",
    url: `${API_HOST_PREFIX}/blogs/${id}`,
    withCredentials: true,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};

const deleteObj = (id) => {
  const config = {
    method: "DELETE",
    url: `${API_HOST_PREFIX}/blogs/${id}`,
    withCredentials: true,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};

const searchCreatedBy = (pageIndex, pageSize, searchQuery) => {
  const config = {
    method: "GET",
    url: `${API_HOST_PREFIX}/blogs/createdby?pageIndex=${pageIndex}&pageSize=${pageSize}&query=${searchQuery}`,
    withCredentials: true,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};

const searchQuery = (pageIndex, pageSize, searchQuery) => {
  const config = {
    method: "GET",
    url: `${API_HOST_PREFIX}/blogs/search?pageIndex=${pageIndex}&pageSize=${pageSize}&query=${searchQuery}`,
    withCredentials: true,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};
const getBlogsByType = (id, payload) => {
  const _logger = debug.extend("BlogService");
  _logger(id);
  const config = {
    method: "GET",
    url: `${API_HOST_PREFIX}/blogs/blogtype/${id}`,
    withCredentials: true,
    data: payload,
    crossdomain: true,
    headers: { "Content-Type": "application/json" },
  };
  return axios(config).then(onGlobalSuccess).catch(onGlobalError);
};

export {
  getPage,
  getBy,
  deleteObj,
  searchCreatedBy,
  searchQuery,
  getBlogsByType,
};
