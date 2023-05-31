/**
 * This function creates a binary tree with the given values.
 * 
 * @param {Array} values - An array of values to be inserted into the binary tree.
 * @returns {Object} - The root node of the binary tree.
 */
function createBinaryTree(values) {
  // Define the node class
  class Node {
    constructor(value) {
      this.value = value;
      this.left = null;
      this.right = null;
    }
  }

  // Define the root node
  let root = null;

  // Insert each value into the binary tree
  for (let i = 0; i < values.length; i++) {
    let value = values[i];
    let node = new Node(value);

    // If the root node is null, set the new node as the root
    if (root === null) {
      root = node;
    } else {
      // Traverse the binary tree to find the correct position to insert the new node
      let current = root;
      while (true) {
        if (value < current.value) {
          if (current.left === null) {
            current.left = node;
            break;
          } else {
            current = current.left;
          }
        } else if (value > current.value) {
          if (current.right === null) {
            current.right = node;
            break;
          } else {
            current = current.right;
          }
        } else {
          break;
        }
      }
    }
  }

  // Return the root node of the binary tree
  return root;
}
