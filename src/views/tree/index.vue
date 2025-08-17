<el-tree :props="treeProps" lazy :load="loadNode" node-key="id" />

<script setup>
const treeProps = {
  children: "children",
  label: "label",
  isLeaf: "isLeaf",
};

const loadNode = (node, resolve) => {
  if (node.level === 0) {
    return resolve([
      { id: 1, label: "一级 1" },
      { id: 2, label: "一级 2" },
    ]);
  }
  if (node.level === 1) {
    setTimeout(() => {
      resolve([{ id: 3, label: "二级 1-1", isLeaf: true }]);
    }, 500);
  }
};
</script>
细说
